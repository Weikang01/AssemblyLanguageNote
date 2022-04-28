### Some representative types of applications:

* Business application for single platform
* Hardware device driver
* Business application for multiple platforms
* Embedded system

### Virtual Machine Example: JVM

* JVM, the main component of Java architecture and the part of JRE. Provides the cross platform functionality to java.
* A software process that converts the compiled Java byte code to machine code.
* Byte code is an intermediary language between Java source and the host system

### .NET CL

* **Common Language Runtime** (CLR) is the virtual machine of Microsoft's .NET framework, responsible for managing the execution of .NET programs.
* <img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155303769.png" alt="image-20220128155303769" style="zoom:50%;" />

### Programming language analogy:

* Each computer has a native machine language (language L0) that runs directly on its hardware
* A more human-friendly language is usually constructed above machine language, called Language L1

### Programs written in L1 can run two different ways:

* Interpretation - L0 program interprets and executes L1 instructions on by one
* Translation - L1 program is completely translated into an L0 program, which then runs on the computer hardware

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220114085041188.png" alt="image-20220114085041188" style="zoom:50%;" />

# **Specific Machine Levels**

### High-Level Language (level 4)

* Application-oriented languages
  * C++, Java, Pascal, Visual Basic...
* powerful statements that translate into multiple assembly language instructions
* Programs compile into assembly language (Level 4)

### Assembly Language (level 3)

* Instruction mnemonics (such as ADD, SUB, and MOV)
* Have a one-to-one correspondence to machine language
* Programs are translated into Instructions Set Architecture Level - machine language (Level 2)
* Assembly language programs are translated (assembled) in their entirety into machine language before they begin to execute

### Instruction Set Architecture (ISA) (Level 2)

* Also known as conventional machine language
* First level at which users can write programs
  * The programs consist of binary values called machine language.
  * Each machine-language instruction is executed
    * Directly by the computer's hardware
    * or by a program embedded in the microprocessor chip called a microprogram
  * Executed by Level 1 (Digital Logic)

### Digital Logic Hardware (Level 1)

CPU, constructed from digital logic gates

System bus

Memory

Implemented using bipolar transistors

### Data Representation

* Binary Numbers
  * Translating between binary and decimal
* Binary Addition
* Integer Storage Sizes
* Hexadecimal Integers
  * Translating between decimal and hexadecimal
  * Hexadecimal subtraction
* Signed Integers
  * Binary subtraction
* Character Storage

### Digits for the Numbering in Hardware and Software Manuals

| System          | Base | Possible Digits                 |
| --------------- | ---- | ------------------------------- |
| **Binary**      | 2    | 0 1                             |
| **Octal**       | 8    | 0 1 2 3 4 5 6 7                 |
| **Decimal**     | 10   | 0 1 2 3 4 5 6 7 8 9             |
| **Hexadecimal** | 16   | 0 1 2 3 4 5 6 7 8 9 A B C D E F |

### Binary Numbers

* Computer stores instructions and data in memory as collections of electronic charges on/off
* Digits are 1 and 0, called bit
  * 1 = true
  * 0 = false
* **Bits** are numbered sequentially starting at zero on the right side and increasing toward the left.
  * MSB - most significant bit
  * LSB - least significant bit

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155334167.png" alt="image-20220128155334167" style="zoom: 50%;" />

**Binary Numbers**

Each digits (bit) is either 1 or 0

Each bit represents a power of 2  ![image-20220128155345833](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155345833.png)

## Translating Binary to Decimal

* Weighted positional notation shows how to calculate the decimal value of each binary bit:

  $dec = (D_{n-1}\times{2^{n-1}})+(D_{n-2}\times{2^{n-2}})+\dots+(D_1\times{2^1})+(D_0\times{2^0})$

* D = binary digit, 0 or 1

* binary 00001001 = decimal 9:

  $(1\times2^3)+(1\times2^0)=9$

## Translating Binary to Decimal

Horner's rule: [Horner's method - Wikipedia](https://en.wikipedia.org/wiki/Horner's_method)

​	$dec = ((\dots((D_{n-1}\times2)+D_{n-2})\times2)+\dots+D_1)\times2+D_0$

​	$10001001_b=128+8+1-137_b$

​	$dec = ((\dots(1\times2)+0)\times2)+\dots+0)\times2+1$

Good for code implementation

Example: $10010101101_b\rightarrow1197_d$

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155403841.png" alt="image-20220128155403841" style="zoom:60%;" />

## Translating Unsigned Decimal to Binary

Repeatedly divide the decimal integer by 2. Each remainder is a binary digit in the translated value:

| Division | Quotient | Remainder |
| -------- | -------- | --------- |
| 37/2     | 18       | 1         |
| 18/2     | 9        | 0         |
| 9/2      | 4        | 1         |
| 4/2      | 2        | 0         |
| 2/2      | 1        | 0         |
| 1        | 0        | 1         |

​	37=100101

### Binary Addition

>    00001100
>
> +10001010
>
>   10010110

## Integer Storage Sizes

**Standard sizes**:

* byte: 8
* word: 16
* doubleword: 32
* quadword: 64

Ranges of Unsigned Integers.

| Storage Type        | Range (low-high)                | Powers of 2       |
| ------------------- | ------------------------------- | ----------------- |
| Unsigned byte       | 0 to 255                        | 0 to $(2^8-1)$    |
| Unsigned word       | 0 to 65,535                     | 0 to $(2^{16}-1)$ |
| Unsigned doubleword | 0 to 4,294,967,295              | 0 to $(2^{32}-1)$ |
| Unsigned quadword   | 0 to 18,446,744,073,709,551,615 | 0 to $(2^{64}-1)$ |

The Dec range is: 0 to $(2^n)-1$ where if the number of bits

## Hexadecimal Integers

### Binary values are represented in hexadecimal.

Binary, Decimal and Hexadecimal Equivalents.

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128124337845.png" alt="image-20220128124337845" style="zoom:67%;" />

## Translating Binary to Hexadecimal

* Each hexadecimal digit corresponds to 4 binary bits.
* Example: Translate the binary integer 1,0110,1010,0111,1001,0100 to hexadecimal:

Try to separate: 0001,0110,1010,0111,1001,0100

| 1    | 6    | A    | 7    | 9    | 4    |
| ---- | ---- | ---- | ---- | ---- | ---- |
| 0001 | 0110 | 1010 | 0111 | 1001 | 0100 |

### Converting Hexadecimal to Decimal

* Multiply each digit by its corresponding power of 16:

  ​	$dec=(D_3\times16^3)+(D_2\times16^2)+(D_1\times16^1)+(D_0\times16^0)$

* Hex 1234 equals $(1\times16^3)+(2\times16^2)+(3\times16^1)+(4\times16^0)$, or decimal 4660.

* Hex 3BA4 equals $(3\times16^3)+(11\times16^2)+(10\times16^1)+(4\times16^0)$, or decimal 15268.

  * Horner's rule: $(((((3\times16)+11)\times16)+10)\times16)+4$

## Converting Decimal to Hexadecimal

| Division | Quotient | Remainder |
| -------- | -------- | --------- |
| 422/16   | 26       | 6         |
| 26/16    | 1        | A         |
| 1/16     | 0        | 1         |

decimal 422 = 1A6 hexadecimal

## Hexadecimal Addition

Divide the sum of two digits by the number base (16). The quotient becomes the carry value, and the remainder is the sum digit.

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155514737.png" alt="image-20220128155514737" style="zoom:67%;" />

## Hexadecimal Subtraction

When a borrow is required from the digit to the left, add 16 (decimal) to the current digit's value:

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155556781.png" alt="image-20220128155556781" style="zoom:67%;" />

## Signed Integers

The highest bit indicates the sign. 1 = negative, 0 = positive

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155627099.png" alt="image-20220128155627099" style="zoom:67%;" />

If the highest digit of a hexadecimal integer is > 7, the value is negative. Examples: 8A, C5, A29D, B1234567

## Forming the Two's Complement

> Negative numbers are stored in two's complement notation
>
> Represents the additive Inverse

| Starting value                             | 00000001            |
| ------------------------------------------ | ------------------- |
| **Step 1: reverse the bits**               | 11111110            |
| **Step 2: add 1 to the value from Step 1** | 11111110 + 00000001 |
| **Sum: two's complement representation**   | 11111111            |

* Note that 00000001 + 11111111 = 0000000-
* Two's Complement operation is **<u>reversible</u>**. Two's Complement of 11111111 is 00000001.

## Binary Subtraction

When subtracting A – B, convert B to its two's complement
Add A to (–B)

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155716452.png" alt="image-20220128155716452" style="zoom:67%;" />

## Learn How To Do the Following:

* Form the two's complement of a hexadecimal for ($-27197_d$)
  * $6A3D_h\rightarrow95C2_h+1\rightarrow95C3_h$
* Convert **signed** binary to decimal
  * $11110000_b\rightarrow00001111+1\rightarrow-16_d$
* Convert **signed** decimal to binary
  * $-43_d\rightarrow(-43_d\rightarrow 00101011_b, 11010100_b+1)\rightarrow11010101_b$
* Convert **signed** decimal to hexadecimal
  * $-43_d\rightarrow D5_h$
* Convert **signed** hexadecimal to decimal
  * $D5_h\rightarrow (2A_h+1 = 2B_h) -43_d$

## Range of Signed Integers

The highest bit is reserved for the sign. This limits the range:

from $-2^{n-1}$  to $2^{n-1}-1$

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128160447449.png" alt="image-20220128160447449" style="zoom:67%;" />

## Character Storage

**Character sets: mapping of characters to integers**

* **Standard ASCII (0-127)**

  * **ASCII**: American Standard Code for Information Interchange
  * Unique 7-bit integer is assigned to each character

* **Extended ASCII (0-255)**

  * The extra bit is used on various computers to create a proprietary character set
  * IBM use values 128 through 255 represent graphics symbols and Greek characters

* **ANSI (0-255)**

  * ANSI: American National Standards Institute
  * The first 128 characters correspond to the letters and symbols on a standard U.S. keyboard.
  * The second 128 characters represent special characters such as letters in international alphabets, accents, currency symbols, and fractions.

* [ASCII - Wikipedia](https://en.wikipedia.org/wiki/ASCII)

* **Unicode (0-65,535)**

  * Universal way of defining characters and symbols
  * Represent a wide variety of international languages in computer software.
  * Defines codes for characters, symbols, and punctuation used in all major languages
  * European alphabetic scripts, Middle Eastern right-to-left scripts, and many scripts of Asia

* **Null-terminated String**

  * It is a string of characters followed by a single byte containing zero.
  * Array of characters followed by a null byte
  * The C and C++ languages use null terminated strings, and many DOS and Windows functions require strings to be in this format.

  # Boolean Algebra

* Based on symbolic logic, designed by George Boole

  * http://en.wikipedia.org/wiki/George_Boole

* Boolean expressions created from:

  * NOT, AND, OR

  <img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128160340029.png" alt="image-20220128160340029" style="zoom:67%;" />

## Operator Precedence

Examples showing the order of operations:

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128160406503.png" alt="image-20220128160406503" style="zoom:67%;" />

# **General Concepts**

## Basic microcomputer design

clock synchronizes CPU operations
control unit (CU) coordinates sequence of execution steps
ALU performs arithmetic and bitwise processing

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154440857.png" alt="image-20220128154440857" style="zoom:67%;" />

## Clock

* Synchronizes all CPU and BUS operations
* Machine (clock) cycle measures time of a single operation
* Clock is used to trigger events
* A cycle duration is the reciprocal of the clock's speed
  * 1 GH: cycle duration 1 billionth of a second, 1 nanosecond
* Wait state, empty cycle

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154430042.png" alt="image-20220128154430042" style="zoom:67%;" />

## Instruction Execution Cycle

Figure: Simplified Pentium CPU Block Diagram.

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154332081.png" alt="image-20220128154332081" style="zoom:67%;" />

## Instruction Execution Cycle

* Fetch
* Decode
* Fetch operands
* Execute
* Store output

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154417436.png" alt="image-20220128154417436" style="zoom:67%;" />

## Reading from Memory

Multiple machine cycles are required when reading from memory, because it responds much slower than the CPU. The steps are:

1. Place the address of the value you want to read on the address bus.
2. Assert (changing the value of) the processor's RD (read) pin.
3. Wai one clock cycle for the memory chips to respond.
4. Copy the data from the data bus into the destination operand.

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154320496.png" alt="image-20220128154320496" style="zoom:67%;" />

## Cache Memory

High-speed expensive static RAM both inside and outside the CPU.

* Level-1 cache: inside the CPU
* Level-2 cache: outside the CPU

**Cache hit**: when data to be read is already in cache memory
**Cache miss**: when data to be read is not in cache memory.
**Online reading**: How Computer Memory Works

* http://computer.howstuffworks.com/computer-memory4.htm

# How a Program Runs

* As soon as the program begins running, it’s called a Process
* A process has its memory and may contains multiple Threads

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154253792.png" alt="image-20220128154253792" style="zoom: 67%;" />

## Multitasking

* OS can run multiple programs at the same time.
* Multiple threads of execution within the same program.
* Scheduler utility assigns a given amount of CPU time to each running program.
* Rapid switching of tasks
  * gives illusion that all programs are running at once
  * the processor must support task switching.

## Round-Robin Scheduler

Task switching: Context, Priority

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154540365.png" alt="image-20220128154540365" style="zoom:80%;" />

# IA-32 Processor Architecture

* Short for **"Intel Architecture, 32-bit"**
* Modes of operation
* Basic execution environment
* Floating-point unit
* Intel Microprocessor history

## Modes of Operation

* Protected mode
  * native mode (Windows, Linus)
* Real-address mode
  * native MS-DOS
* System management mode
  * power management, system security, diagnostics
* Virtual-8060 mode
  * hybrid of Protected
  * each program has its own 8089 computer
  * allows the execution of real mode applications that are incapable of running directly in protected mode while the processor is running a protected mode operating system.

## Basic Execution Environment

* Addressable memory
* General-purpose registers
* Index and base registers
* Specialized register uses
* Status flags
* Floating-point, MMX, XMM registers

## Addressable Memory

* Protected mode
  * The range of memory is 4 GB
  * 32-bit address
* Read-address and Virtual-8086 modes
  * 1 MB space
  * 20-bit address

## General-Purpose Registers

Named storage locations inside the CPU, optimized for speed.

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154626197.png" alt="image-20220128154626197" style="zoom:80%;" />

## Accessing Parts of Registers

Use 8-bit name, 16-bit name, or 32-bit name

Applies to EAX, EBX, ECX, and EDX

![image-20220128154652399](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154652399.png)

## Index and Base Registers

Some registers have only a 16-bit name for their lower half:

| 32-bit | 16-bit |
| ------ | ------ |
| ESI    | SI     |
| EDI    | DI     |
| EBP    | BP     |
| ESP    | SP     |

## Some Specialized Register Uses

* **General-Purpose**
  * EAX - accumulator
  * ECX - loop counter
  * ESP - stack pointer
  * ESI, EDI - index registers
  * EBP - extended frame pointer (stack)
* **Segment**
  * CS - code segment
  * DS - data segment
  * SS - stack segment
  * ES, FS, GS - additional segments
* **EIP - instruction pointer**
  * IP for 16-bit
* **EFLAGS**
  * status and control flags
  * each flag is a single binary bit

## Status Flags

* The **Carry** flag (CF) is set when the result of an ***unsigned*** arithmetic operation is too large to fit into the destination.
* The **Overflow** flag (OF) is set when the result of a ***signed*** arithmetic operation is too large or too small to fit into the destination. 
* The **Sign** flag (SF) is set when the result of an arithmetic or logical operation generates a negative result.
* The **Zero** flag (ZF) is set when the result of an arithmetic or logical operation generates a result of zero.
* The **Auxiliary Carry** flag (AC) is set when an arithmetic operation causes a carry from bit 3 to bit 4 in an 8-bit operand.
* The **Parity** flag (PF) is set if the lease-significant byte in the result contains an even number of 1 bits. Otherwise, PF is clear. In general, it is used for error checking when there is a possibility that data might be altered or corrupted.
  * If the result of the last operation were 26 (11010 in binary), the parity flag would be 0 since the number of set bits is odd. Similarly, if the result where 10 (1010 in binary) then the parity flag would be 1.

## Floating-Point, MMX, XXM Registers

* Eight 80-bit floating-point data registers
  * ST(0), ST(1),...,ST(7)
    * <img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128154717444.png" alt="image-20220128154717444" style="zoom:80%;" />
  * arranged in a stack
  * used for all floating-point arithmetic
* Eight 64-bit MMX registers
  * a single instruction, multiple data [(SIMD) instruction set architecture][https://en.wikipedia.org/wiki/SIMD]
  * MMX instructions operate in parallel on the data values contained in MMX registers
* Eight 128-bit XMM registers for single-instruction multiple-data(SIMD) operations

# CISC and RISC

* CISC - complex instruction set
  * large instruction set
  * high-level operations
  * requires microcode interpreter
  * examples: Intel 80x86 family
* RISC - reduced instruction set
  * simple, atomic instructions
  * small instruction set
  * directly executed by hardware
  * examples:
    * ARM (Advanced RISC Machines)
      * [ARM Assembly Language Programming][http://www.peter-cockerell.net/aalp/html/frames.html]

# IA-32 Memory Management

## Real-address mode

* 1 MB RAM maximum addressable
* Application programs can access any area of memory
* Single tasking
* Supported by MS-DOS operating system

## Calculating linear addresses

## Protected mode

* 4 GB addressable RAM
  * (00000000 to FFFFFFFFh)
* Each program assigned a memory partition which is protected from other programs
* Designed for multitasking
* Supporting by Linux & MS-Windows

## Paging

* Supported directly by the CPU
* Divides each segment into 4096-byte blocks called **pages**
* Sum of all programs can be larger than physical memory
* Part of running program is in memory, part is on disk
* **Virtual memory manager** (VMM) - OSS utility that manages the loading and unloading of pages
* **Page fault** - issued by CPU when a page must be loaded from disk

## 64-Bit Processors

### 64-Bit Operation Modes

* Compatibility mode - can run existing 16-bit and 32-bit applications (windows supports only 32-bit apps in this mode)
* 64-bit mode - Windows 64 uses this

### Basic Execution Environment

* addresses can be 64 bits (48 bits, in practice)
* 16 64-bit general purpose registers
* 64-bit instruction pointer

# 64-Bit General Purpose Registers

32-bit general purpose registers:

* EAX, EBX, ECX, EDI, ESI, EBP, ESP, R8D, R9D, R10D, R11D, R12D, R13D, R14D, R15D

64-bit general purpose registers:

* RAX, RBX, RCX, RDX, RDI, RSI, RBP, RSP, R8, R9, R10, R11, R12, R13, R14, R15

# 64-bit Processors

**Intel64**

* 64-bit linear address space
* Intel: Pentium Extreme, Xeon, Celeron D, Pentium D, Core 2, and Core i7

**IA-32e Mode**

* Compatibility mode for legacy 16- and 32-bit applications
* 64-bit Mode uses 64-bit addresses and operands

# Components of an IA-32 Microcomputer

* **Motherboard**
* **Video output**
* **Memory**
* **Input-output ports**

## Motherboard

* CPU socket External cache memory slots
* Main memory slots
* BIOS chips
* Sound synthesizer chip (optional)
* Video controller chip (optional)
* IDE, parallel, serial, USB, video, keyboard, joystick, network, and mouse connectors
* PCI(Peripheral Component Interconnect) but connectors (expansion cards)

![image-20220121090517439](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220121090517439.png)

## Video Output

* Video controller
  * on motherboard, or on expansion card
  * AGB (accelerated graphics port technology)
* Video memory (VRAM)
* Video CRT Display
  * uses raster scanning
  * horizontal retrace
  * vertical retrace
* Direct digital LCD monitors
  * no raster scanning required

### Sample Video Controller (ATI Corp.)

* 128-bit 3D graphics performance powered by RAGE™ 128 PRO 
* 3D graphics performance 
* Intelligent TV-Tuner with Digital VCR 
* TV-ON-DEMAND™ 
* Interactive Program Guide 
* Still image and MPEG-2 motion video capture 
* Video editing 
* Hardware DVD video playback 
* Video output to TV or VCR 

![image-20220128155012767](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155012767.png)

## Memory

* ROM
  * read-only memory
* EPROM
  * erasable programmable read-only memory, ultraviolet light
* Dynamic RAM (Random Access Memory) (DRAM)
  * inexpensive; must be refreshed constantly
* Static RAM (SRAM)
  * expensive; used for cache memory; no refresh required
* Video RAM (VRAM)
  * dual ported; optimized for constant video refresh
* CMOS RAM
  * complementary metal-oxide semiconductor
  * system setup information

## Input-Output Ports

* USB (universal serial bus)
  * intelligent high-speed connection to devices
  * 480 megabits/second (2.0), 12 mb/s (1.0)
  * USB hub connects multiple devices
  * ***enumeration***: computer queries devices
  * supports ***hot*** connections
* Parallel
  * short cable, high speed
  * common for printers
  * bidirectional, parallel data transfer
  * Intel 8255 controller chip
* Serial
  * RS-232 serial port
  * one bit at a time
  * uses long cables and modems
  * 16550 UART (universal asynchronous receiver transmitter)
  * programmable in assembly language

# Device Interfaces

* ATA (***advanced technology attachment***) host adapters
  * intelligent drive electronics (hard drive, CDROM)
* SATA (Serial ATA)
  * inexpensive, fast, bidirectional
* FireWire
  * high speed (800MB/sec), many devices at once
* Bluetooth
  * small amounts of data, short distances, low power usage
* Wi-Fi (Wireless Ethernet)
  * IEEE 802.11 standard, faster than Bluetooth

# Levels of Input-Output

* Level 3: High-level language function
  * examples: C++, Java
  * portable, convenient, not always the fastest
* Level 2: Operating system
  * Application Programming Interface (API)
  * extended capabilities, lots of details to master
* Level 1: BIOS
  * drivers that communicate directly with devices
  * OS security may prevent application-level code from working at this level

## Displaying a String of Characters

When a HLL program displays a string of characters, the following steps take place:

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155102877.png" alt="image-20220128155102877" style="zoom:67%;" />

## Programming levels

Assembly language programs can perform input-output at each of the following levels:

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128155126030.png" alt="image-20220128155126030" style="zoom:80%;" />

# Mnemonics and Operands

* Instruction Mnemonics
  * memory aid
  * examples: MOV, ADD, SUB, MUL, INC, DEC
* Operands
  * constant
  * constant expression
  * register
  * memory (data label)
* Constants and constant expressions are often called **immediate values**

# Integer Constants

* Optional leading + or - sign
* Binary, decimal, hexadecimal, or octal digits
* Common radix characters:
  * h - hexadecimal
  * d - decimal
  * b - binary
  * r - encoded real
    * [sign] integer.[integer]\[exponent]
    * 2., +3.0, -44.2E+05, 26.E5
    * At least one digit and a decimal point are required
* Examples: 30d, 6Ah, 42, 1101b

Hexadecimal beginning with letter: **0**A5h

* r - encoded real: to write a real number, at least we need to type a number and a dot "."
* hexadecimal: beginning with 0

# Integer Expressions

### Operators and precedence levels:

| Operator | Name              | Precedence Level |
| -------- | ----------------- | ---------------- |
| ( )      | parentheses       | 1                |
| +, -     | unary plus, minus | 2                |
| *, /     | multiply, divide  | 3                |
| MOD      | modulus           | 3                |
| +, -     | add, subtract     | 4                |

### Examples:

| Expression          | Value |
| ------------------- | ----- |
| 16 / 5              | 3     |
| - (3 + 4) * (6 - 1) | -35   |
| -3 + 4 * 6 - 1      | 20    |
| 25 mod 3            | 1     |

# Character and String Constants

* Enclose character in single or double quotes
  * 'A', "x"
  * ASCII character = 1 byte
* Enclose strings in single or double quotes
  * "ABC"
  * 'xyz'
  * Each character occupies a single byte
* Embedded quotes:
* 'Say "Goodnight," Gracie'

# Reserved Words and Identifiers

* Reserved words cannot be used as identifiers
  * Instruction mnemonics, such as MOV, ADD, and MUL
  * Register names
  * Directives, which tell MASM how to assemble programs
  * Attributes, which provide size and usage information for variables and operands. Examples are BYTE and WORD
  * Operators, used in constant expressions (+, -, *, ...)
  * Predefined symbols, such as @data, which return constant integer values at assembly time
  * See MASM reference in Appendix A
    * Microsoft Macro Assembler Reference
  * Identifiers
    * 1-247 characters, including digits
    * not case sensitive
    * first character must be a letter, _, @, ? or $

# Directives

* Commands that are recognized and acted upon by the assembler

  * Not part of the Intel instruction set
  * Used to declare code, data areas, select memory model, declare procedures, etc.
  * not case sensitive

* Different assemblers have different directives

  * NASM not the same as MASM, for example

* The .DATA directive identifies the area of a program containing variables:

  ```assembly
  .data
  ```

* The .STACK directive identifies the area of a program holding the runtime stack, setting its size:

  ```assembly
  .stack 100h
  ```

* Example:

  ```assembly
  myVar DWORD 26	; DWORD directive
  mov eax, myVar	; MOV instruction
  ```

The DWORD directive tells the assembler to reserve space in the program for a doubleword variable.

The MOV instruction, on the other hand, executes at runtime, copying the contents of myVar to the EAX register.

# **Instructions**

* Assembled into machine code by assembler
* Executed at ***runtime*** by the CPU
* We use the Intel IA-32 instruction set
* An instruction contains:
  * Label			(optional)
  * Mnemonic	(required)
  * Operand	   (depends on the instruction)
  * Comment	 (optional)
  * [Label:] Mnemonic Operand(s) [; Comment]

# Labels

* Act as place markers

  * marks the address (offset) of code and data

* Follow identifier rules

* Data label

  * Data Labels A data label identifies the location of a variable, providing a convenient way to reference the variable in code. The following, for example, defines a label named count:

    ```assembly
    count DWORD 100
    ```

  * must be unique

* Code label

  * in the code area of a program (where instructions are located) (followed by colon)

  * target of jump and loop instructions

  * example

    ```assembly
    target:
    	mov ax, bx
    	...
    	jmp target
    ```

# Mnemonics and Operands

## Instruction Mnemonics

* memory aid
* examples:
  * mov Move (assign) one value to another
  * add Add two values
  * sub Subtract one value from another
  * mul Multiply two values
  * jmp Jump to a new location
  * call Call a procedure

## Operands

* Assembly language can have between zero and three operands

  * constant

  * constant expression

  * register

  * memory (data label)

  * Constants and constant expressions are often called ***immediate values***

    | Example | Operand Type                     |
    | ------- | -------------------------------- |
    | 96      | Constant (***immediate value***) |
    | 2 + 4   | Constant expression              |
    | eax     | Register                         |
    | count   | Memory                           |

# Instruction Format Examples

* No operand

  ```assembly
  std	; set Carry flag
  ```

* One operand

  ```assembly
  inc eax	; register
  inc myByte	; memory
  ```

* Two operands

  ```assembly
  add ebx, ecx	; register, register
  sub myByte, 25	; memory, constant
  add eax, 36*25	; register, constant-expression
  mov count,ebx	; move EBX to count
  ```

* Three operands

  ```assembly
  imul eax,ebx,5	; EBX multiplied by 5, and the result stored in EAX.
  ```

# Comments

* Comments are good!
  * explain the program's purpose
  * when it was written, and by whom
  * revision information
  * tricky coding techniques
  * application-specific explanations
* Single-line comments
  * begin with semicolon (;)
* Multi-line comments
  * begin with COMMENT directive and a programmer-chosen character
  * end with the same programmer-chosen character

```assembly
; this is a single line comment
COMMENT $
	this is a multiline comment
$
```

```assembly
; AddTwo.asm
.386
.model flat, stdcall
.stack 4096
ExitProcess PROTO, dwExitCode:DWORD
.code
main PROC
	mov eax, 5	; move 5 to the EAX register
	add eax, 6	; add  6 to the EAX register
	
	INVOKE ExitProcess, 0
main ENDP
END main
```

## Example Output

**Showing registers and flags in the debugger:**

```output
EAX = 0000000B EBX = 7EFDE000 ECX = 00000000 EDX = 0040100A ESI = 00000000 EDI = 00000000 EIP = 00401054 ESP = 0018FF8C EBP = 0018FF94 EFL = 00000202 

OV = 0 UP = 0 EI = 1 PL = 0 ZR = 0 AC = 0 PE = 0 CY = 0 
```

## 16-bit FLAGS Register

| **Bit** | **11** | **10** | **9**  | **8** | **7**  | **6**  | **5** | **4**  | **3** | **2**  | **1** | **0**  |
| ------- | ------ | ------ | ------ | ----- | ------ | ------ | ----- | ------ | ----- | ------ | ----- | ------ |
| **Txt** | **OF** | **DF** | **IF** |       | **SF** | **ZF** |       | **AF** |       | **PF** |       | **CF** |
| **VS**  | **OV** | **UP** | **EI** |       | **PL** | **ZR** |       | **AC** |       | **PE** |       | **CY** |

Bit0: CF - Carry Flag 					Bit1: always a 1 
Bit2: PF - Parity Flag 					Bit3: always a 0 
Bit4: AF - Auxiliary (Carry) 			Bit5: always a 0 
Bit6: ZF - Zero Flag 					  Bit7: SF - Sign Flag 
Bit8: TF - Trap Flag (no use)		 Bit9: IF - Interrupt Flag 
Bit10: DF - Direction Flag 			 Bit11: OF – Overflow

# Suggested Coding Standards

### Some approaches to capitalization

* capitalize nothing
* capitalize everything
* capitalize all reserved words, including instruction mnemonics and register names
* capitalize only directives and operators

### Other suggestions

* descriptive identifier names
* spaces surrounding arithmetic operators
* blank lines between procedures

### Indentation and spacing

* code and data labels - no indentation
* executable instructions - indent 4-5 spaces
* comments: right side of page, aligned vertically
* 1-3 spaces between instruction and its operands
  * ex: mov ax, bx
* 1-2 blank lines between procedures

### Program Template

```assembly
; Program Template

; Description:
; Author:
; Creation Date:
; Revisions:
; Date:
; Modified by:

; Template.asm
.386
.model flat, stdcall
.stack 4096
ExitProcess PROTO, dwExitCode:DWORD
.code
main PROC
	; write your code here
	INVOKE ExitProcess, 0
main ENDP
END main
```

## Assemble-Link Execute Cycle

* The following diagram describes the steps from creating a source program through executing the compiled program.
* If the source code is modified, Steps 2 through 4 must be repeated.
* The assembler contains a **preprocessor** to process directives, etc.

![image-20220128161826130](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128161826130.png)



# Listing File

* Listing file suitable for printing, and contains a copy of the program's
  * source code,
  * with line numbers,
  * offset addresses,
  * segment names,
  * translated machine code,
  * and a symbol table
* Use it to see how your program is compiled
* Example: addSub.lst

# Map File

* Information about each program segment:
  * starting address
  * ending address
  * size
  * segment type
* Example: addSub.map (16-bit version)

# The NOP Instruction

* It takes up 1 byte of program storage and doesn't do any work. It is sometimes used by compilers and assembler
* Code alignment: Align the code to even-address boundaries
* Check from a list file
* Debug from Disassembly window:

```disassembly
00000000 66 8B C3 mov ax, bx
00000003 90 nop				; align next instruction
00000004 8B D1 mov edx, ecx
```

# Intrinsic Data Types

* Describes a set of values that can be assigned to variables and expressions of the given type.
* BYTE, SBYTE
  * 8-bit unsigned integer; 8-bit signed integer
* WORD, SWORD
  * 16-bit unsigned & signed integer
* DWORD, SDWORD
  * 32-bit unsigned & signed integer
* QWORD
  * 64-bit integer
* TBYTE
  * 80-bit integer
* REAL4
  * 4-byte IEEE short real
* REAL8
  * 8-byte IEEE long real
* REAL10
  * 10-byte IEEE extended real

# Data Definition Statement

* A data definition statement sets aside storage in memory for a variable.
* May optionally assign a name (label) to the data
* Syntax:
  * [name] directive initializer [,initializer]...
  * **value1 BYTE 10**
* All initializers become binary data in memory

# Defining BYTE and SBYTE Data

Each of the following defines a single byte of storage:

```assembly
value1 BYTE 'A'			; character constant
value2 BYTE 0			; smallest unsigned byte
value1 BYTE 255			; largest unsigned byte
value1 SBYTE -128		; smallest signed byte
value1 SBYTE +127		; largest signed byte
value1 BYTE ?			; unitialized byte
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
; * MASM does not prevent you from initializing a BYTE with a
;	negative value, but it's considered poor style.
; * If you declare a SBYTE variable, the Microsoft debugger
;	automatically display its value in decimal with a leading
;	sign.
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
```

## Defining Byte Arrays

Examples that use multiple initializers:

```assembly
list1 BYTE 10, 20, 30, 40
list2 BYTE 10, 20, 30, 40
	  BYTE 50, 60, 70, 80
list3 BYTE ?, 32, 41h, 00100010b
list4 BYTE 0Ah, 20h, 'A', 22h	; different radixes
```

# Defining Strings

* A string is implemented as an array of characters

  * For convenience, it is usually enclosed in quotation marks
  * It often will be null-terminated (null byte containing 0)

* Examples:

  ```assembly
  str1 BYTE "Enter your name", 0
  str2 BYTE 'Error: holting program', 0
  str3 BYTE 'A', 'E', 'I', 'O', 'U'
  greeting BYTE "Welcome to the Encryption Demo program "
  		BYTE "created by Kip Irvine.", 0
  ```

### To continue a single string across multiple lines, end each line with a comma:

```assembly
menu BYTE "Checking Account", 0dh, 0ah, 0dh, 0ah,
	"1. Create a new account", 0dh, 0ah,
	"2. Open an existing account", 0dh, 0ah,
	"3. Credit the account", 0dh, 0ah,
	"4. Debit the account", 0dh, 0ah,
	"5. Exit", 0dh, 0ah,
	"Choice> ", 0
```

End-of-line character sequence:

* 0Dh = carriage return
* 0Ah = line feed

CR/LF: When written to standard output, they move the cursor to the left column of the line following the current line.

```assembly
str1 BYTE "Enter your name:		", 0Dh, 0Ah,
	BYTE "Enter your address:	", 0

newLine BYTE 0Dh, 0Ah, 0
```

# Using the DUP Operator

Use DUP to allocate (create space for) an array or string. Syntax: counter DUP (argument)

Counter and argument must be constants or constant expressions

```assembly
var1 BYTE 20 DUP(0)			; 20 bytes, all equal to zero
var2 BYTE 20 DUP(?)			; 20 bytes, uninitialized
var3 BYTE 4 DUP("STACK")	; 20 bytes: "STACKSTACKSTACKSTACK"
var4 BYTE 10,3 DUP(0), 20	; 5 bytes
```

# Defining WORD and SWORD Data

Define storage for 16-bit integers

* or double characters
* single value or multiple values

```assembly
word1 WORD 65535			; largest unsigned value
word2 SWORD -32768			; smallest signed value
word3 WORD ?				; uninitialized, unsigned
word4 WORD "AB"				; double characters
myList WORD 1,2,3,4,5		; double characters
array WORD 5 DUP(?)			; uninitialized array
```

# Defining DWORD and SDWORD Data

### Storage definitions for signed and unsigned 32-bit integers:

```assembly
val1 DWORD 12345678h		; unsigned
val2 SDWORD -2147483648		; signed
val3 DWORD 20 DUP(?)		; unsigned array
val4 SWORD -3,-2,-1,0,1		; signed array
```

# Defining QWORD TBYTE, Real Data

Storage definitions for quadwords, tenbyte values, and real numbers:

```assembly
quad1 QWORD      1234567812345678h
val1  TBYTE      100000000123456789Ah
rVal1 REAL4      -2.1
rVal2 REAL8      2.3E-260
rVal3 REAL10     4.6E+4096
ShortArray REAL4 20 DUP(0.0)
```

# Little Endian Order

All data types larger than a byte store their individual bytes in reverse order. The least significant byte occurs at the first (lowest) memory address.

Example:

```assembly
val1 DWORD 12345678h
```

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128161617586.png" alt="image-20220128161617586" style="zoom:67%;" />

# Big Endian Order

All data types larger than a byte store their individual bytes in "usual" order. The most significant byte occurs at the first (lowest) memory address.

Example:

```assembly
val1 DWORD 12345678h
```

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220128161640775.png" alt="image-20220128161640775" style="zoom: 67%;" />

# Adding Variables to AddSub

* [Irvin Libraries][http://asmirvine.com/gettingStartedVS2019/index.htm]

```assembly
; This program adds and subtracts 32-bit unsigned
; integers and stores the sum in a variable.
INCLUDE Irvine32.inc
.data
val1 DWORD 10000h
val2 DWORD 40000h
val3 DWORD 20000h
finalVal DWORD ?
.code
main PROC
	mov eax,val1		; start with 10000h
	add eax,val2		; add 40000h
	sub eax,val3		; subtract 20000h
	mov finalVal,eax	; store the result (30000h)
	call DumpRegs		; display the registers
	exit
main ENDP
END main
```

## Declaring Uninitialized Data

Use the .data? directive to declare an uninitialized data segment:

```assembly
.data?
```

Within the segment, declare variables with "?" initializers:

```assembly
smallArray DWORD 10 DUP(?)
```

**Advantage: the program's EXE file size is reduced.**

## Equal-Sign Directive
name = expression
* expression is a 32-bit integer (expression or constant)
* may be redefined
* name is called a symbolic constant

good programming style to use symbols

```assembly
COUNT = 500
.
.
mov ax,COUNT
```

## Redefine with Equal-Sign

```assembly
count = 5
mov al, count

...
count = 100
mov al, count

...

Count = “This is a count!”
```

## Calculating the Size of a Byte Array

current location counter: $

* subtract address of list
* difference is the number of bytes

```assembly
list BYTE 10,20,30,40
ListSize = ($ - list)
```

## Calculating the Size of a Word Array

Divide total number of bytes by 2 (the size of a word)

* ($ - list) is byte count

```assembly
list WORD 1000h,2000h,3000h,4000h
ListSize = ($ - list) / 2
```

## Calculating the Size of a Doubleword Array

Divide total number of bytes by 4 (the size of a doubleword)

```assembly
list DWORD 1,2,3,4
ListSize = ($ - list) / 4
```
# EQU Directive
* Define a symbol as either a number or text expression.
* Cannot be redefined
```assembly
PI EQU <3.1416>
pressKey EQU <"Press any key to continue...",0>
.data
prompt BYTE pressKey
```
```assembly
Matrix1 EQU 10*10
Matrix2 EQU <10*10>
.data
M1 word Matrix1 ; M1 word 100
M2 word Matrix2 ; M2 word 10*10
```
# TEXTEQU Directive
* Define a symbol as either an integer or text expression.
* Called a **text macro**
* Can be redefined
```assembly
continueMsg TEXTEQU <"Do you wish to continue (Y/N)?">
rowSize = 5
.data
prompt1 BYTE continueMsg
count TEXTEQU %(rowSize * 2)		; evaluates the expression
setupAL TEXTEQU <mov al,count>

.code
setupAL		; generates: "mov al,10"
```

# 64-Bit Programming

MASM supports 64-bit programming, although the following directives are not permitted:

* INVOKE, ADDR, .model, .386, .stack

## 64-Bit Version of AddTwoSum

```assembly
; AddTwoSum_64.asm - Chapter 3 example.
ExitProcess PROTO
.data
sum DWORD 0
.code
main PROC
	mov eax, 5
	add eax, 6
	mov sum, eax
	mov ecx, 0
	call ExitProcess
main ENDP
END
```

# Data Transfers, addressing, and arithmetic

## Operand Types

* **Immediate** – a constant integer (8, 16, or 32 bits)
  * value is encoded within the instruction
* **Register** – the name of a register
  * register name is converted to a number and encoded within the instruction
* **Memory** – reference to a location in memory
  * memory address is encoded within the instruction, or a register holds the address of a memory location

### Instruction Operand Notation

![image-20220211083457978](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220211083457978.png)

### Direct Memory Operands

* A direct memory operand is a **named reference** to storage in memory
* The named reference (**label**) is automatically **dereferenced** by the assembler

```assembly
.data
var1 BYTE 10h
.code
mov al,var1		; AL = 10h
mov al,[var1]	; alternate format, AL = 10h
```

### MOV Instruction

* Move from source to destination. Syntax:

  ```assembly
  ; MOV destination,source
  ```

* No more than **one memory** operand permitted

* **CS**, **EIP**, and **IP** cannot be the destination

* No **immediate** to segment reg moves

* Both operands must be the **same** size.

```assembly
; MOV reg,reg
; MOV mem,reg
; MOV reg,mem
; MOV mem,imm
; MOV reg,imm

.data
count BYTE 100
wVal  WORD 2
.code
	mov bl,count
	mov ax,wVal
	mov count,al
```

The following code are incorrect:

```assembly
.data
bVal  BYTE   100
bVal2 BYTE   ?
wVal  WORD   2
dVal  DWORD  5
.code
	mov ds,45		; immediate move to DS not permitted
	mov esi,wVal	; size mismatch
	mov eip,dVal	; EIP cannot be the destination
	mov 25,bVal		; immediate value cannot be destination
	mov bVal2,bVal	; memory-to-memory move not permitted
```

### Zero Extension

> When you copy a **smaller** value into a **larger** destination, the **MOVZX** instruction fills (extends) the upper half of the destination with **zeros**.

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220211084806343.png" alt="image-20220211084806343" style="zoom:67%;" />

```assembly
.data
val BYTE 10001111b

.code
movzx ax, val 
```

* The destination must be a **register**.
* The source **cannot** be **immediate**.

### Sign Extension

> The **MOVSX** instruction fills the upper half of the destination with a copy of the source operand's sign bit.

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220211084823553.png" alt="image-20220211084823553" style="zoom:67%;" />

```assembly
mov bl,10001111b
movsx ax, bl
```

​    The destination must be a **register**.
​    The source **cannot** be **immediate**.

### XCHG Instruction

> **XCHG** exchanges the values of two **operands**. At least one operand must be a **register**. **No immediate** operands are permitted.

```assembly
.data
var1 WORD 1000h
var2 WORD 2000h
.code
xchg ax,bx		; exchange 16-bit regs
xchg ah,al		; exchange 8-bit regs
xchg var1,bx	; exchange mem, reg
xchg eax,ebx	; exchange 32-bit regs

xchg var1,var2	; error: two memory operands
```

### Direct-Offset Operands

> A **constant offset** is added to a **data label** to produce an effective address (**EA**). The address is **dereferenced** to get the value inside its **memory** location.

```assembly
.data
arrayB BYTE 10h,20h,30h,40h
.code
mov al,arrayB+1			; AL = 20h
mov al,[arrayB+1]		; alternative notation
```

A **constant** offset is added to a data label to produce an effective address (EA). The address is dereferenced to get the value inside its memory location.

```assembly
.data
arrayW  WORD 1000h,2000h,3000h	; word has 2 byte
arrayD  DWORD 1,2,3,4			; dword has 4 byte
.code
mov ax,[arrayW+2]		; AX = 2000h
mov ax,[arrayW+4]		; AX = 3000h
mov eax,[arrayD+4]		; EAX = 00000002h

; Will the following statements assemble?
mov ax,[arrayW-2]		; 
mov eax,[arrayD+16]		; the assembler just retrieves a byte of memory outside the array.
```

Write a program that rearranges the values of three doubleword  values in the following array as: 3, 1, 2.

```assembly
.data
arrayD DWORD 1,2,3
```

* Step1: copy the first value into EAX and exchange it with the value in the second position.

```assembly
mov eax,arrayD			; 1 => eax
xchg eax,[arrayD+4]		; 1, 1, 3    eax=2
```

* Step 2: Exchange EAX with the third array value and copy the value in EAX to the first array position.

```assembly
xchg eax,[arrayD+8]		; 1, 1, 2    eax=3
mov arrayD,eax			; eax => arrayD
```

#### Evaluate this . . .

* We want to write a program that adds the following three bytes:

  ```assembly
  .data
  myBytes BYTE 80h,66h,0A5h
  ```

* What is your evaluation of the following code?

  ```assembly
  mov al,myBytes
  add al,[myBytes+1]
  add al,[myBytes+2]
  ```

* What is your evaluation of the following code?

  ```assembly
  mov ax,myBytes
  add ax,[myBytes+1]
  add ax,[myBytes+2]
  ```

Another approach:

```assembly
.data
myBytes BYTE 80h,66h,0A5h
```

* How about the following code. Is anything missing?

  ```assembly
  movzx ax,myBytes
  mov   bl,[myBytes+1]
  add   ax,bx
  mov   bl,[myBytes+2]
  add   ax,bx			; AX = sum
  ; Yes: Move zero to BX before the MOVZX instruction.
  ```

### Addition and Subtraction

* INC and DEC Instructions
* ADD and SUB Instructions
* NEG Instruction
* Implementing Arithmetic Expressions
* Flags Affected by Arithmetic
  * Zero
  * Sign
  * Carry
  * Overflow

### INC and DEC Instructions

* Add 1, subtract 1 from destination operand
  * operand may be register or memory
* INC destination
  * Logic: destination <= destination + 1
* DEC destination
  * Logic: destination <= destination – 1

```assembly
.data
myWord  WORD 1000h
myDword DWORD 10000000h
.code
	inc myWord 	; 1001h
	dec myWord	; 1000h
	inc myDword	; 10000001h

	mov ax,00FFh
	inc ax	; AX = 0100h
	mov ax,00FFh
	inc al	; AX = 0000h
```

Show the value of the destination operand after each of the following instructions executes:

```assembly
.data
myByte BYTE 0FFh, 0
.code
	mov al,myByte	; AL = FFh
	mov ah,[myByte+1]	; AH = 00h
	dec ah	; AH = FFh
	inc al	; AL = 00h
	dec ax	; AX = FEFFh
```

### ADD and SUB Instructions

* **ADD** destination, source
  * Logic: destination <= destination + source
* **SUB** destination, source
  * Logic: destination <= destination – source
* Same operand **rules** as for the MOV instruction

```assembly
.data
var1 DWORD 10000h
var2 DWORD 20000h
.code	; ---EAX---
	mov eax,var1	; 00010000h
	add eax,var2 	; 00030000h
	add ax,0FFFFh	; 0003FFFFh
	add eax,1	; 00040000h
	sub ax,1	; 0004FFFFh
```

### NEG (negate) Instruction

**Reverses** the **sign** of an operand. Operand can be a **register** or **memory** operand. (Like converting to its **Two’s Complement**)

```assembly
.data
valB BYTE -1
valW WORD +32767
.code
	mov al,valB	; AL = -1
	neg al	; AL = +1
	neg valW	; valW = -32767
```

### NEG Instruction and the Flags

> The processor implements  NEG using the following internal operation:
>
> ```assembly
> SUB 0,operand
> ```
>
> Any **nonzero** operand causes the **Carry** flag to be set.

```assembly
.data
valB BYTE 1,0
valC SBYTE -128
.code
	neg valB	; CF = 1, OF = 0
	neg [valB + 1]	; CF = 0, OF = 0
	neg valC	; CF = 1, OF = 1
```

### Implementing Arithmetic Expressions

**HLL** compilers **translate** mathematical expressions into **assembly** language. You can do it also. For example: 

```c
Rval = -Xval + (Yval – Zval)
```

```assembly
Rval DWORD ?
Xval DWORD 26
Yval DWORD 30
Zval DWORD 40
.code
	mov eax,Xval		
	neg eax 	; EAX = -26
	mov ebx,Yval
	sub ebx,Zval 	; EBX = -10
	add eax,ebx
	mov Rval,eax 	; -36
```

Translate the following expression into assembly language. Do not permit Xval, Yval, or Zval to be modified: 

```c
Rval = Xval - (-Yval + Zval)
```

Assume that all values are signed doublewords.

```assembly
mov ebx, Yval
neg ebx
add ebx, Zval
mov eax, Xval
sub eax, ebx
mov Rval, eax
```

### Flags Affected by Arithmetic

* The ALU has a number of **status** flags that reflect the outcome of arithmetic (and bitwise) operations
  * based on the contents of the **destination** operand
* Essential flags:
  * Zero flag – set when **destination** equals **zero**
  * Sign flag – set when destination is **negative**
  * Carry flag – set when **unsigned** value is **out** of range
  * Overflow flag – set when **signed** value is **out** of range
* The **MOV instruction never affects the flags**.

## Concept Map

![image-20220211092026355](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220211092026355.png)

You can use diagrams such as these to express the relationships between assembly language concepts.

### Zero Flag (ZF)

> The Zero flag is set when the result of an operation produces **zero** in the **destination** operand.  

```assembly
mov cx,1
sub cx,1 	; CX = 0, ZF = 1
mov ax,0FFFFh
inc ax 	; AX = 0, ZF = 1
inc ax 	; AX = 1, ZF = 0
```

Remember...

* A flag is **set** when it equals 1. 
* A flag is **clear** when it equals 0.

### Sign Flag (SF)

> The Sign flag is set when the **destination** operand is **negative**. The flag is clear when the destination is positive. 

```assembly
mov cx,0
sub cx,1 	; CX = -1, SF = 1
add cx,2 	; CX = 1, SF = 0
```

The sign flag is a copy of the destination's highest bit:

```assembly
mov al,0
sub al,1            ; AL = 11111111b, SF = 1
add al,2            ; AL = 00000001b, SF = 0
```

### Overflow and Carry Flags: A Hardware Viewpoint

>  MSB = Most Significant Bit (high-order bit)
>  XOR = eXclusive-OR operation
>  NEG = Negate (same as SUB  0,operand )

* How the ADD instruction affects OF and CF:
  * CF  = (carry out of the MSB)
  * OF  = (carry out of the MSB) XOR (carry into the MSB)           
* How the SUB instruction affects OF and CF:
  * CF  = INVERT (carry out of the MSB) 
  * When a larger unsigned integer is subtracted from a smaller one
  * negate the source and add it to the destination
  * OF  = (carry out of the MSB) XOR (carry into the MSB) 

### Carry Flag (CF)

> The Carry flag is set when the **result** of an operation generates an **unsigned** value that is out of range (too **big** or too **small** for the destination operand).

```assembly
mov al,0FFh
add al,1	; CF = 1, AL = 00

; Try to go below zero:

mov al,0
sub al,1	; CF = 1, AL = FF
```

How about this, Why? 				

```assembly
mov al,2
sub al,1	; CF = 0, AL = 1
```

For each of the following marked entries, show the values of the destination operand and the Sign, Zero, and Carry flags:

```assembly
mov ax,00FFh
add ax,1	; AX= 0100h SF=0 ZF=0 CF=0
sub ax,1	; AX= 00FFh SF=0 ZF=0 CF=0
add al,1	; AL= 00h   SF=0 ZF=1 CF=1
mov bh,6Ch
add bh,95h	; BH= 01h   SF=0 ZF=0 CF=1

mov al,2
sub al,3	; AL= FFh   SF=1 ZF=0 CF=1
```

### Overflow Flag (OF)

> The Overflow flag is **set** when the signed result of an operation is **invalid** or **out** of range.

```assembly
; Example 1
mov al,+127
add al,1	; OF = 1,   AL = ??

; Example 2
mov al,7Fh	; OF = 1,   AL = 80h
add al,1
```

> The two examples are identical at the binary level because 7Fh equals +127. To determine the value of the destination operand, it is often easier to calculate in hexadecimal.

### A Rule of Thumb

When adding two integers, remember that the Overflow flag is only set when . . .

* Two positive operands are added and their sum is negative
* Two negative operands are added and their sum is positive
* Overflow never occurs when the signs of two addition operands are different.

What will be the values of the Overflow flag?

```assembly
mov al,80h
add al,92h	; OF = 1, AL=02

mov al,-2
add al,+127	; OF = 0
; Notice: -2 is 1111 1110 (254)
```

What will be the values of the given flags after each operation?

```assembly
mov ax,8000h
add ax,2	; CF =0	OF =0

mov ax,0
sub ax,2	; CF =1	OF =0

mov al,-5
sub al,+125	; CF =0	OF =1 AL =7E
```

## Data-Related Operators and Directives

* OFFSET Operator
* PTR Operator
* TYPE Operator
* LENGTHOF Operator
* SIZEOF Operator
* LABEL Directive

### OFFSET Operator

> **OFFSET** returns the distance in **bytes**, of a **label** from the **beginning** of its **enclosing** segment
>
> * Protected mode: 32 bits
> * Real mode: 16 bits
>
> <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220211093920726.png" alt="image-20220211093920726" style="zoom:50%;" />
>
> The Protected-mode programs we write use only a single segment (flat memory model).

#### OFFSET Examples

Let's assume that the data segment begins at 00404000h:

```assembly
.data
bVal BYTE ?
wVal WORD ?
dVal DWORD ?
dVal2 DWORD ?

.code
mov esi,OFFSET bVal 	; ESI = 00404000
mov esi,OFFSET wVal 	; ESI = 00404001
mov esi,OFFSET dVal 	; ESI = 00404003
mov esi,OFFSET dVal2	; ESI = 00404007
```

#### Relating to C/C++

> The value returned by **OFFSET** is a **pointer**. Compare the following code written for both C++ and assembly language:

```c
// C++ version:

char array[1000];
char * p = array;
```

```assembly
; Assembly language:

.data
array BYTE 1000 DUP(?)
.code
mov	 esi,OFFSET array
```

### ALIGN Directive

* Aligns a **variable** on a **byte**, **word**, **dword**, or **paragraph** boundary
* Padding to 1, ,2, 4, or 16 bytes in data segments 
* The CPU can process data stored at even numbered addresses more quickly than those at odd-numbered addresses.

```assembly
.data
	bVal	BYTE 10h	; 0000 0000
	ALIGN 2
	wVal	WORD 20h	; 0000 0002
	bVal2	BYTE 30h	; 0000 0004
	ALIGN 4
	dVal	DWORD 50h	; 0000 0008
	bVal3	BYTE  60h	; 0000 000C
	ALIGN 4
	dVal2	DWORD 70h	; 0000 0010
```

### PTR Operator

> **Overrides** the default **type** of a label (variable). Provides the **flexibility** to access **part** of a variable.

```assembly
.data
myDouble DWORD 12345678h
.code
; mov ax,myDouble 			; error – why?

mov ax,WORD PTR myDouble			; loads 5678h

mov WORD PTR myDouble,4321h		; saves 4321h
mov EBX, myDouble
; What is myDouble now? 
```

Little endian order is used when storing data in memory 12344321h (memory 21 43 34 12)

#### Little Endian Order

* Little endian order refers to the **way** Intel stores **integers** in **memory**.
* Multi-byte integers are stored in reverse order, with the **least** significant byte stored at the **lowest** address
* For example, the doubleword 12345678h would be stored as:

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220211094513326.png" alt="image-20220211094513326" style="zoom:67%;" />

When integers are loaded from memory into registers, the bytes are automatically **re-reversed** into their correct positions.

#### PTR Operator Examples

```assembly
.data
myDouble DWORD 12345678h
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220211094609533.png" alt="image-20220211094609533" style="zoom:50%;" />

```assembly
mov al,BYTE PTR  myDouble			; AL = 78h
mov al,BYTE PTR [myDouble+1]		; AL = 56h
mov al,BYTE PTR [myDouble+2]		; AL = 34h
mov ax,WORD PTR  myDouble			; AX = 5678h
mov ax,WORD PTR [myDouble+2]		; AX = 1234h
```

> PTR can also be used to **combine elements** of a **smaller** data type and **move** them into a **larger** operand. The CPU will automatically **reverse** the bytes.

```assembly
.data
myBytes BYTE 12h,34h,56h,78h

.code
mov ax,WORD PTR [myBytes]		; AX = 3412h
mov ax,WORD PTR [myBytes+2]		; AX = 7856h
mov eax,DWORD PTR myBytes		; EAX = 78563412h
```

Write down the value of each destination operand:

```assembly
.data
varB BYTE 65h,31h,02h,05h
varW WORD 6543h,1202h
varD DWORD 12345678h

.code
mov ax,WORD PTR [varB+2]	; a. 0502h
mov bl,BYTE PTR varD		; b. 78h
mov bl,BYTE PTR [varW+2]	; c. 02h
mov ax,WORD PTR [varD+2]	; d. 1234h
mov eax,DWORD PTR varW		; e. 12026543h
mov ax, word ptr varD+1		; f. 3456h
```

### TYPE Operator

> The **TYPE** operator **returns** the **size**, in **bytes**, of a single **element** of a data declaration.

```assembly
.data
var1 BYTE ?
var2 WORD ?
var3 DWORD ?
var4 QWORD ?

.code
mov eax,TYPE var1	; 1
mov eax,TYPE var2	; 2
mov eax,TYPE var3	; 4
mov eax,TYPE var4	; 8
```

### LENGTHOF Operator

> The **LENGTHOF** operator **counts** the number of **elements** in a single data declaration.

```assembly
.data	LENGTHOF
byte1  BYTE 10,20,30		; 3
array1 WORD 30 DUP(?),0,0	; 32
array2 WORD 5 DUP(3 DUP(?))	; 15
array3 DWORD 1,2,3,4		; 4
digitStr BYTE "12345678",0	; 9

.code
mov ecx,LENGTHOF array1	; 32
```

### SIZEOF Operator

> The **SIZEOF** operator **returns** a value that is equivalent to multiplying **LENGTHOF** by **TYPE**.

```assembly
.data							;SIZEOF
byte1  BYTE 10,20,30		 	; 3
array1 WORD 30 DUP(?),0,0		; 64
array2 WORD 5 DUP(3 DUP(?))		; 30
array3 DWORD 1,2,3,4			; 16
digitStr BYTE "12345678",0		; 9

.code
mov ecx,SIZEOF array1			; 64
```

### Spanning Multiple Lines

> A data declaration **spans multiple** lines if each line (except the last) ends with a **comma**. The LENGTHOF and SIZEOF operators include all lines belonging to the **declaration**:

```assembly
.data
array WORD 10,20,
	30,40,
	50,60

.code
mov eax,LENGTHOF array	; 6
mov ebx,SIZEOF array	; 12
```

In the following example, array identifies only the first WORD declaration. Compare the values returned by LENGTHOF and SIZEOF here to those in the previous slide:

```assembly
.data
array	WORD 10,20
	WORD 30,40
	WORD 50,60

.code
mov eax,LENGTHOF array	; 2
mov ebx,SIZEOF array	; 4
```

### LABEL Directive

* Assigns an alternate label name and type to an existing storage location
* LABEL does not allocate any storage of its own
* Removes the need for the PTR operator

```assembly
.data
dwList   LABEL DWORD
wordList LABEL WORD
intList  BYTE 00h,10h,00h,20h
.code
mov eax,dwList	; 20001000h
mov cx,wordList	; 1000h
mov dl,intList	; 00h
```

```assembly
.data
v16 label word
v32 DWORD 12345678h
.code
mov ax, v16		; ax = 5678h
mov dx, v16 +2 	; dx = 1234h

.data
val label dword
v1 WORD 5678h
v2 WORD 1234h
.code
mov eax, val	; eax = 12345678h
```

## Indirect Addressing

* Indirect Operands
* Array Sum Example
* Indexed Operands
* Pointers

### Indirect Operands

* Indirect operand can be any **32-bit general-purpose** register (EAX, EBX, ECX, EDX, ESI, EDI, EBP, and ESP) surrounded by **brackets**
* An indirect operand **holds** the **address** of a variable, usually an **array** or **string**. It can be dereferenced (just like a **pointer**).

```assembly
.data
val1 BYTE 10h,20h,30h
.code
mov esi,OFFSET val1
mov al,[esi]	; dereference ESI (AL = 10h)

inc esi
mov al,[esi]	; AL = 20h

inc esi
mov al,[esi]	; AL = 30h
```

* Use PTR to clarify the size attribute of a memory operand.
* The assembler does not know whether ESI points to a byte, word, doubleword, or some other size. 

```assembly
.data
myCount WORD 0

.code
mov esi,OFFSET myCount
inc [esi]	; error: ambiguous
inc WORD PTR [esi]	; ok
```

Should PTR be used here? 

```assembly
add [esi],20
```

yes, because [esi] could point to a byte, word, or doubleword

### Array Sum Example

> **Indirect operands** are ideal for **traversing** an array. Note that the register in brackets must be **incremented** by a value that **matches** the array type.

```assembly
.data
arrayW WORD 1000h,2000h,3000h
.code
mov esi,OFFSET arrayW
mov ax,[esi]
add esi,2	; or: add esi,TYPE arrayW
add ax,[esi]
add esi,2
add ax,[esi]	; AX = sum of the array
```

### Indexed Operands

An indexed operand adds a constant to a register to generate an effective address. There are two notational forms:

```assembly
;[label + reg]			label[reg]
```

```assembly
.data
arrayW WORD 1000h,2000h,3000h
.code
	mov esi,0
	mov ax,[arrayW + esi] 		; AX = 1000h
	mov ax,arrayW[esi]		; alternate format
	add esi,2
	add ax,[arrayW + esi]
	;etc.
```

### Index Scaling

> You can **scale** an indirect or indexed operand to the **offset** of an array element. This is done by multiplying the index by the array's **TYPE**: 

```assembly
.data
arrayB BYTE  0,1,2,3,4,5
arrayW WORD  0,1,2,3,4,5
arrayD DWORD 0,1,2,3,4,5

.code
mov esi,4
mov al,arrayB[esi*TYPE arrayB]		; 04
mov bx,arrayW[esi*TYPE arrayW]		; 0004
mov edx,arrayD[esi*TYPE arrayD]		; 00000004
```

### Pointers

> You can **declare** a pointer variable that contains the **offset** of another **variable**.

```assembly
.data
arrayW WORD 1000h,2000h,3000h
ptrW DWORD arrayW
.code
	mov esi,ptrW
	mov ax,[esi]	; AX = 1000h
```

Alternate format:

```assembly
ptrW DWORD OFFSET arrayW
```

### TYPEDEF

> lets you **create** a **user-defined** type that has all the **status** of a **built-in** type when defining variables

```assembly
PBYTE TYPEDEF PTR BYTE   		; PBYTE is a pointer to bytes
.data
ArrayB BYTE 10, 20, 30, 40, 50 
P1 PBYTE ?
P2 PBYTE ArrayB 
```

## JMP and LOOP Instructions

* JMP Instruction
* LOOP Instruction
* LOOP Example
* Summing an Integer Array
* Copying a String

### JMP Instruction

* JMP is an **unconditional** jump to a **label** that is usually within the  same **procedure**.

* Syntax: JMP target

* Logic: EIP <= target

* Example:

  ```assembly
  top:
  	.
  	.
  	jmp top
  ```

  A jump outside the current procedure must be to a special type of label called a **global label** (see Section 5.5.2.3 for details).

### LOOP Instruction

* The LOOP instruction creates a **counting** loop
* Syntax: LOOP target
* Logic:
  * ECX => ECX – 1
  * if ECX != 0, jump to target
* Implementation: 
* The assembler calculates the **distance**, in **bytes**, between the **offset** of the following instruction and the offset of the target label. It is called the relative offset.
* The relative offset is added to **EIP**.

### LOOP Example

The following loop calculates the sum of the integers 5 + 4 + 3 +2 + 1:

```assembly
00000000  66 B8 0000		mov  ax,0  
00000004  B9 00000005		mov  ecx,5

00000009  66 03 C1	L1:	add  ax,cx
0000000C  E2 FB		loop L1
0000000E
```

> When LOOP is assembled, the current location = 0000000E (offset of the next instruction).  –5 (FBh) is added to the the current location, causing a jump to location 00000009:
> 	00000009 <= 0000000E + FB

What will be the final value of AX?

```assembly
	mov ax,6
	mov ecx,4
L1:
	inc ax
	loop L1
```

Answer: 10

### Nested Loop

> If you need to code a **loop within a loop**, you must save the **outer** loop counter's ECX value. In the following example, the outer loop executes 100 times, and the inner loop 20 times.

```assembly
.data
count DWORD ?
.code
	mov ecx,100	; set outer loop count
L1:
	mov count,ecx	; save outer loop count
	mov ecx,20	; set inner loop count
L2:	.
.
loop L2	; repeat the inner loop
	mov ecx,count	; restore outer loop count
	loop L1	; repeat the outer loop
```

### Summing an Integer Array

The following code calculates the sum of an array of 16-bit integers.

```assembly
.data
intarray WORD 100h,200h,300h,400h
.code
	mov edi,OFFSET intarray	; address of intarray
	mov ecx,LENGTHOF intarray	; loop counter
	mov ax,0	; zero the accumulator
L1:
	add ax,[edi]	; add an integer
	add edi,TYPE intarray	; point to next integer
	loop L1	; repeat until ECX = 0
```

### Copying a String

The following code copies a string from source to target:

```assembly
.data
source  BYTE  "This is the source string",0
target  BYTE  SIZEOF source DUP(0)

.code
	mov  esi,0					; index register
	mov  ecx,SIZEOF source		; loop counter
L1:
	mov  al,source[esi]			; get char from source
	mov  target[esi],al			; store it in the target
	inc  esi					; move to next character
	loop L1						; repeat for entire string
```

### 64-Bit Programming

* **MOV** instruction in 64-bit mode **accepts** operands of 8, 16, 32, or **64** bits
* When you move a 8, 16, or 32-bit constant to a 64-bit register, the **upper** bits of the destination are **cleared**.
* When you move a memory operand into a 64-bit register, the results vary:
  * **32-bit** move **clears** high bits in destination
  * **8-bit** or 16-bit move **does not** affect high bits in destination
* **MOVSXD** sign **extends** a 32-bit value into a 64-bit destination register
* The **OFFSET** operator generates a **64-bit** address
* **LOOP** uses the 64-bit **RCX** register as a counter
* **RSI** and **RDI** are the most common **64-bit index** registers for **accessing** arrays.
* **ADD** and **SUB** affect the **flags** in the same way as in **32-bit** mode
* You can use **scale** factors with indexed operands.

## Summary

* Data Transfer
  * **MOV** – data transfer from source to destination
  * **MOVSX**, **MOVZX**, **XCHG**
* Operand types
  * direct, direct-offset, indirect, indexed
* Arithmetic
  * INC, DEC, ADD, SUB, NEG
  * Sign, Carry, Zero, Overflow flags
* Operators
  * OFFSET, PTR, TYPE, LENGTHOF, SIZEOF, TYPEDEF
* **JMP** and **LOOP** – branching instructions

# Procedures

## Overview

* Stack Operations
* Defining and Using Procedures
* Linking to an External Library
* The Irvine32 Library
* Program Design Using Procedures
* 64-Bit Assembly Programming

## Stack Operations

* Runtime Stack
* PUSH Operation
* POP Operation
* PUSH and POP Instructions
* Using PUSH and POP
* Example: Reversing a String
* Related Instructions

### Runtime Stack

* Imagine a stack of plates . . .

  * plates are only added to the top

  * plates are only removed from the top

  * LIFO structure

    <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218084025442.png" alt="image-20220218084025442" style="zoom:67%;" />

* Managed by the CPU, using two registers

  * SS (stack segment)

  * ESP (stack pointer) (SP in Real-address mode)

    <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218084448638.png" alt="image-20220218084448638" style="zoom:67%;" />

### PUSH Operation

* A 32-bit **push** operation **decrements** the stack pointer by **4** and **copies** a value into the **location** pointed to by the stack pointer.

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218085130180.png" alt="image-20220218085130180" style="zoom:67%;" />

* Same stack after pushing two more integers:

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218085524268.png" alt="image-20220218085524268" style="zoom:67%;" />

  The stack grows **downward**. The area **below** ESP is always **available** (unless the stack has **overflowed**).

### POP Operation

* Copies **value** at stack[ESP] into a **register** or variable.

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218085743561.png" alt="image-20220218085743561" style="zoom:67%;" />

### PUSH and POP Instructions

* PUSH syntax:
  * PUSH r/m16
  * PUSH r/m32
  * PUSH imm32
* POP syntax:
  * POP r/m16
  * POP r/m32

> Irvine32 library always pushes 32-bit value

### Using PUSH and POP

**Save** and **restore** registers when they contain **important** values. PUSH and POP instructions occur in the **opposite** order.

```assembly
INCLUDE Irvine32.inc
.data
array WORD 8,9,10,11,0FFFFh 
.code 
main PROC
	push esi		; push registers, for example esi = 10A230h
	push ecx
	push ebx
	
	mov esi,OFFSET array 		; esi = address of array
	mov ecx,LENGTHOF array ;5 
	mov ebx,TYPE array ;2 
	call DumpMem
	
	pop ebx			; restore registers
	pop ecx
	pop esi			; esi = 10A230h
main ENDP
```

#### DumpMem PROC

> Writes a range of memory to standard output in hexadecimal.
> Call arguments: 
> ESI = starting offset
> ECX = number of units
> EBX = bytes/unit (1,2,or 4) 
> Return argument: None 
> Example: Dump a word array 

```assembly
.data
array WORD 8,9,10,11,0FFFFh 
.code 
mov esi,OFFSET array 
mov ecx,LENGTHOF array ;5 
mov ebx,TYPE array ;2 
call DumpMem

```

### Example: Nested Loop

> When **creating** a nested loop, push the outer loop counter before entering the inner loop:

```assembly
	mov ecx,100	; set outer loop count
L1:		; begin the outer loop
	push ecx	; save outer loop count

	mov ecx,20	; set inner loop count
L2:		; begin the inner loop
	;
	;
	loop L2	; repeat the inner loop

	pop ecx	; restore outer loop count
	loop L1	; repeat the outer loop
```

### Example: Reversing a String

* Use a **loop** with **indexed** addressing

* **Push** each character on the stack

* Start at the beginning of the string, **pop** the stack in **reverse** order, **insert** each character **back** into the **string**

* Source code

  ```assembly
  .data
  aName byte "Abraham Lincoln",0
  nameSize = ($ - aName) - 1
  .code
  main proc
  
  ; Push the name on the stack.
  
  	mov	 ecx,nameSize
  	mov	 esi,0
  
  L1:	movzx eax,aName[esi]	; get character
  	push eax				; push on stack
  	inc	 esi
  	loop L1
  
  ; Pop the name from the stack in reverse
  ; and store it in the aName array.
  
  mov	 ecx,nameSize
  	mov	 esi,0
  
  L2:	pop  eax				; get character
  	mov	 aName[esi],al		; store in string
  	inc	 esi
  	loop L2
  
  	Invoke ExitProcess,0
  main endp
  ```

  

* Q: Why must each character be put in EAX before it is pushed?

  > Because only word (16-bit) or doubleword (32-bit) values can be pushed on the stack.

### Related Instructions

* PUSHFD and POPFD
  * push and pop the EFLAGS register
* PUSHAD pushes the 32-bit general-purpose registers on the stack 
  * order: EAX, ECX, EDX, EBX, ESP, EBP, ESI, EDI
* POPAD pops the same registers off the stack in reverse order
  * PUSHA and POPA do the same for 16-bit registers

#### PUSHFD and POPFD

* Usually we want to:

  ```assembly
  pushfd
  ;
  ; do something
  ;
  popfd
  ```

  * But problems are…
    * Skip out?
    * Unpaired ops?

* Less error-prone?

```assembly
.data
savedFlags DWORD ?
.code
pushfd
pop savedFlags 
;
; do something
;
push savedFlags 
popfd
```

## Defining and Using Procedures

* Creating Procedures
* Documenting Procedures
* Example: SumOf Procedure
* CALL and RET Instructions
* Nested Procedure Calls
* Local and Global Labels
* Procedure Parameters
* Flowchart Symbols
* USES Operator

### Creating Procedures

* **Large problems** can be **divided** into smaller tasks to make them more **manageable**

* A ***procedure*** is the ASM **equivalent** of a Java or C++ **function**

* Following is an assembly language procedure named **sample**:

  ```assembly
  sample PROC
  .
  .
  ret
  sample ENDP
  ```

### Documenting Procedures

> Suggested **documentation** for each procedure:

* A **description** of all **tasks** accomplished by the procedure.
* **Receives**: A list of **input** parameters; **state** their usage and **requirements**.
* **Returns**: A **description** of values returned by the procedure.
* **Requires**: Optional list of requirements called **preconditions** that must be **satisfied before** the procedure is called.

> If a procedure is called **without** its preconditions **satisfied**, it will  probably not produce the expected **output**.

### Example: SumOf Procedure

```assembly
;---------------------------------------------------------
SumOf PROC
;
; Calculates and returns the sum of three 32-bit integers.
; Receives: EAX, EBX, ECX, the three integers. May be
; signed or unsigned.
; Returns: EAX = sum, and the status flags (Carry,
; Overflow, etc.) are changed.
; Requires: nothing
;---------------------------------------------------------
add eax,ebx
add eax,ecx
ret
SumOf ENDP
```

To call SumOf, prepare arguments: EAX, EBX, ECX

```assembly
mov eax,10
mov ebx,20
mov ecx,30
call SumOf
WriteDec
```

### CALL and RET Instructions

* The **CALL** instruction calls a procedure 
  * **pushes** offset of next instruction on the stack
  * **copies** the address of the called procedure into **EIP**
* The **RET** instruction **returns** from a **procedure**
  * **pops** top of stack into **EIP**

#### Call-Ret Example

```assembly
main PROC
00000020 call MySub
00000025 mov eax,ebx
; 0000025 is the offset of the 
; instruction immediately 
; following the CALL
; instruction
.
.
main ENDP

MySub PROC
00000040 mov eax,edx
; 00000040 is the offset of 
; the first instruction inside
; MySub
.
.
ret
MySub ENDP
```

> The CALL instruction pushes 00000025 onto the stack, and loads 00000040 into EIP

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218093546511.png" alt="image-20220218093546511" style="zoom:67%;" />

> The RET instruction pops 00000025 from the stack into EIP
>
> (stack shown before RET executes)

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218093612440.png" alt="image-20220218093612440" style="zoom:67%;" />

### Nested Procedure Calls

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218093648736.png" alt="image-20220218093648736" style="zoom:67%;" />

> By the time Sub3 is called, the stack contains all three return addresses:

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218093713901.png" alt="image-20220218093713901" style="zoom:67%;" />

### Local and Global Labels

A **local label** is **visible** only to statements **inside** the same **procedure**. A **global** label is visible **everywhere**.

```assembly
main PROC
	jmp L2	; error
L1::	; global label
	exit
main ENDP

sub2 PROC
L2:		; local label
	jmp L1	; ok
	ret
sub2 ENDP
```

### Procedure Parameters

* A good procedure might be **usable** in many **different** programs
  * but **not** if it refers to **specific** variable names
* **Parameters** help to make procedures **flexible** because **parameter** values can **change** at runtime

> The **ArraySum** procedure calculates the sum of an array. It makes two references to specific variable names:

```assembly
ArraySum PROC
	mov esi,0				; array index
	mov eax,0				; set the sum to zero
	mov ecx,LENGTHOF myarray  ; set number of elements

L1:	add eax,myArray[esi]	; add each integer to sum
	add esi,4				; point to next integer
	loop L1					; repeat for array size

	mov theSum,eax			; store the sum
	ret
ArraySum ENDP
```

This version of ArraySum returns the sum of any doubleword  array whose address is in ESI. The sum is returned in EAX:

```assembly
ArraySum PROC
; Receives: ESI points to an array of doublewords, 
;           ECX = number of array elements.
; Returns:  EAX = sum
;-----------------------------------------------------
	mov eax,0		; set the sum to zero

L1:	add eax,[esi]	; add each integer to sum
	add esi,4		; point to next integer
	loop L1			; repeat for array size

	ret
ArraySum ENDP
```

### USES Operator

* **Lists** the **registers** that will be **preserved** 

  ```assembly
  ArraySum PROC USES esi ecx
  	mov eax,0	; set the sum to zero
  	;etc.
  ```

  MASM generates the code shown in **gray**:

  ```assembly
  ArraySum PROC
  	push esi
  	push ecx
  	;.
  	;do something
  	;.
  	pop ecx
  	pop esi
  	ret
  ArraySum ENDP
  ```

### When Not To Push A Register

The sum of the **three registers** is stored in **EAX** on line (3), but the POP instruction replaces it with the starting value of **EAX** on line (4):

```assembly
SumOf PROC		; sum of three integers
    push eax	; 1
    add eax,ebx	; 2
    add eax,ecx	; 3
    pop eax		; 4
    ret
SumOf ENDP
```

## Linking to an External Library

* What is a Link Library?
* How the Linker Works

### What is a Link Library?

* A **file** containing **procedures** that have been **compiled** into **machine** code
  * **constructed** from one or more **OBJ** files
* To build a library, . . .
  * start with one or more **ASM** source **files**
  * assemble each into an **OBJ** file
  * create an **empty** library file (extension .LIB)
  * add the OBJ file(s) to the library file, using the Microsoft **LIB utility**

> Take a quick look at Irvine32.asm in the \Irvine\Examples\Lib32 folder.

### How the Linker Works

* Your programs **link** to **Irvine32.lib** using the **linker** command inside a **batch** file named **make32.bat**.

* Notice the two LIB files: Irvine32.lib, and kernel32.lib

  * the latter is part of the Microsoft **Win32 *Software Development Kit*** (SDK)

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218094803035.png" alt="image-20220218094803035" style="zoom:67%;" />

## The Irvine32 Library

### Calling Irvine32 Library Procedures

* **Call** each **procedure** using the **CALL** instruction. Some procedures require **input** arguments. The **INCLUDE** directive copies in the **procedure** prototypes (declarations).
* The following example displays "1234" on the console:

```assembly
INCLUDE Irvine32.inc
.code
	mov  eax,1234h	; input argument
	call WriteHex	; show hex number
	call Crlf		; end of line
```

### Irvine Library Help

* A Windows help file showing:
  * Irvine Library Procedures
    * Procedure Purpose
    * Calling & Return  Arguments
    * Example of usage
* Directly look up procedures
  * examples\Lib32\Irvine32.asm

### Example 1

* Clear the screen, delay the program for 500 milliseconds, and dump the registers and flags.

```assembly
.code
	call Clrscr   ; Clears console, locates cursor at upper left corner

	mov  eax,500
	call Delay   ; Pauses program execution for n millisecond interval
	call DumpRegs
```

Sample output:

```output
EAX=00000613 EBX=00000000 ECX=000000FF EDX=00000000
ESI=00000000 EDI=00000100 EBP=0000091E ESP=000000F6
EIP=00401026 EFL=00000286 CF=0 SF=1 ZF=0 OF=0
```

### Example 2

* Display a null-terminated string and move the cursor to the beginning of the next screen line.

```assembly
.data
str1 BYTE "Assembly language is easy!",0

.code
	mov  edx,OFFSET str1
	call WriteString ; Writes null-terminated string to console window
	call Crlf; Writes end of line sequence to standard output
```

* Display a null-terminated string and move the cursor to the beginning of the next screen line (use embedded CR/LF)

```assembly
.data
str1 BYTE "Assembly language is easy!",0Dh,0Ah,0

.code
	mov  edx,OFFSET str1
	call WriteString
```

### Example 3

* Display an unsigned integer in binary, decimal, and hexadecimal, each on a separate line.

```assembly
IntVal = 35	
.code
	mov  eax,IntVal
	call WriteBin	; display binary
	call Crlf
	call WriteDec	; display decimal
	call Crlf
	call WriteHex	; display hexadecimal
	call Crlf
```

Sample output:

```output
0000 0000 0000 0000 0000 0000 0010 0011
35
23
```

### Example 4

* Input a string from the user. EDX points to the string and ECX specifies the maximum number of characters the user is permitted to enter.

```assembly
.data
fileName BYTE 80 DUP(0)

.code
	mov  edx,OFFSET fileName
	mov  ecx,SIZEOF fileName – 1
	call ReadString ; Reads string from stdin, terminated by [Enter]
```

> A null byte is automatically appended to the string.

### Example 5

* Generate and display ten pseudorandom signed integers in the range 0 – 99. Pass each integer to WriteInt in EAX and display it on a separate line.

```assembly
.code
	mov ecx,10			; loop counter

L1:	mov  eax,100		; ceiling value
	call RandomRange	; generate random int
	call WriteInt		; display signed int
	call Crlf			; goto next display line
	loop L1				; repeat loop
```

### Example 6

* Display a null-terminated string with yellow characters on a blue background. 				

```assembly
.data
str1 BYTE "Color output is easy!",0

.code
	mov  eax,yellow + (blue * 16)
	call SetTextColor
	mov  edx,OFFSET str1
	call WriteString
	call Crlf
```

> The background color is multiplied by 16 before being added to the foreground color.

## Program Design Using Procedures

* Top-Down Design (**functional decomposition**) involves the following:
  * **design** your program **before** starting to code
  * **break** large **tasks** into **smaller** ones
  * use a **hierarchical** structure based on **procedure** calls
  * test **individual** procedures **separately**

### Integer Summation Program

**Description**: Write a program that prompts the user for multiple 32-bit integers, stores them in an array, calculates the sum of the array, and displays the sum on the screen.

Main steps:

* **Prompt** user for **multiple** integers
* **Calculate** the **sum** of the **array**
* **Display** the sum

```assembly
Main
	Clrscr				; clear screen
	PromptForIntegers
		WriteString		; display string
		ReadInt 		; input integer
	ArraySum 			; sum the integers
	DisplaySum
		WriteString		; display string
		WriteInt		; display integer
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220218100603177.png" alt="image-20220218100603177" style="zoom:67%;" />

(gray indicates library procedure)

### Random Integer: TestLib2.asm

* Random32
* RandomRange

### Performance Timing: TestLib3.asm

* Calculate the elapsed time of execution
* Design procedures 
* Use push and pop to access the loop counter
* Control the display position by calling Gotoxy

## 64-Bit Assembly Programming

* The Irvine64 Library
* Calling 64-Bit Subroutines
* The x64 Calling Convention

### The Irvine64 Library

* **Crlf**: Writes an end-of-line sequence to the console.
* **Random64**: Generates a 64-bit pseudorandom integer. 
* **Randomize**: Seeds the random number generator with a unique value.
* **ReadInt64**: Reads a 64-bit signed integer from the keyboard.
* **ReadString**: Reads a string from the keyboard. 
* **Str_compare**: Compares two strings in the same way as the CMP instruction.
* **Str_copy**: Copies a source string to a target location. 
* **Str_length**: Returns the length of a null-terminated string in RAX.
* **WriteInt64**: Displays the contents in the RAX register as a 64-bit signed decimal integer.
* **WriteHex64**: Displays the contents of the RAX register as a 64-bit hexadecimal integer.
* **WriteHexB**: Displays the contents of the RAX register as an 8-bit hexadecimal integer .
* **WriteString**: Displays a null-terminated ASCII string. 

### Calling 64-Bit Subroutines

* **Place** the first four **parameters** in **registers**

* Add **PROTO** directives at the top of your program

  * examples:

  ```assembly
  ExitProcess PROTO 	; located in the Windows API
  WriteHex64 PROTO 	; located in the Irvine64 library
  ```

### The x64 Calling Convention

* Must **use** this with the **64-bit** Windows **API**

* **CALl** instruction **subtracts** 8 from RSP

* First four parameters must be **placed** in **RCX, RDX, R8, and R9**

* **Caller** must **allocate** at least **32 bytes** of shadow space on the **stack**

* When calling a **subroutine**, the stack **pointer** must be **aligned** on a **16-byte** boundary.

  > See the CallProc_64.asm example program.

## Summary

* Procedure – **named block of executable code**
* Runtime stack – **LIFO** structure
  * **holds return** addresses, parameters, local variables
  * **PUSH** – add value to stack
  * **POP** – remove value from stack
* Use the **Irvine32** library for all **standard** I/O and data conversion

# Conditional Processing

* Boolean and Comparison Instructions
* Conditional Jumps
* Conditional Loop Instructions
* Conditional Structures
* Application: Finite-State Machines
* Conditional Control Flow Directives

## Boolean and Comparison Instructions

* CPU Status Flags
* AND Instruction
* OR Instruction
* XOR Instruction
* NOT Instruction
* Applications
* TEST Instruction 
* CMP Instruction

### Status Flags - Review

* The **Zero** flag is set when the result of an operation equals zero.
* The **Carry** flag is set when an instruction generates a result that is too large (or too small) for the destination operand.
* The **Sign** flag is set if the destination operand is negative, and it is clear if the destination operand is positive.
* The **Overflow** flag is set when an instruction generates an invalid signed result (bit 7 carry is XORed with bit 6 Carry).
* The **Parity** flag is set when an instruction generates an even number of 1 bits in the low byte of the destination operand.
* The **Auxiliary** Carry flag is set when an operation produces a carry out from bit 3 to bit 4

### AND Instruction

* Performs a **Boolean AND** operation between each **pair** of **matching** bits in two **operands**
* Syntax:
  * AND destination, source
    (same operand types as MOV)

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304083648240.png" alt="image-20220304083648240" style="zoom:67%;" />

AND

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304083713488.png" alt="image-20220304083713488" style="zoom:67%;" />

### OR Instruction

* Performs a Boolean OR operation between each pair of matching bits in two operands
* Syntax:
  * OR destination, source

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304083807701.png" alt="image-20220304083807701" style="zoom:67%;" />

OR

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304083818732.png" alt="image-20220304083818732" style="zoom:67%;" />

### XOR Instruction

* Performs a Boolean exclusive-OR operation between each pair of matching bits in two operands
* Syntax:
  * XOR destination, source

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304083857383.png" alt="image-20220304083857383" style="zoom:67%;" />

XOR

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304083909847.png" alt="image-20220304083909847" style="zoom:67%;" />

### NOT Instruction

* Performs a Boolean NOT operation on a single destination operand
* Syntax:
  * NOT destination

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304083938687.png" alt="image-20220304083938687" style="zoom:67%;" />

NOT

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304083950364.png" alt="image-20220304083950364" style="zoom:67%;" />

### Bit-Mapped Sets

* Binary bits indicate set membership
* Efficient use of storage
* Also known as bit vectors

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304084044626.png" alt="image-20220304084044626" style="zoom:67%;" />

### Bit-Mapped Set Operations

* Set Complement

  ```assembly
  mov eax,SetX
  not eax
  ```

* Set Intersection

  ```assembly
  mov eax,setX
  and eax,setY
  ```

* Set Union

  ```assembly
  mov eax,setX
  or  eax,setY
  ```

### Applications

* Task: Convert the character in AL to upper case.
* Solution: Use the AND instruction to clear bit 5.

```assembly
mov al,'a'			; AL = 01100001b
and al,11011111b	; AL = 01000001b
```

* Task: Convert a binary decimal byte into its equivalent ASCII decimal digit. 6 = 54 IN ASCII
* Solution: Use the OR instruction to set bits 4 and 5.

```assembly
mov al,6             ; AL = 00000110b
or  al,00110000b     ; AL = 00110110b The ASCII digit '6' 
```

* Task: Turn on the keyboard CapsLock key
* Solution: Use the OR instruction to set bit 6 in the keyboard flag byte at 0040:0017h in the BIOS data area.

```assembly
mov ax,40h	; BIOS segment
mov ds,ax
mov bx,17h	; keyboard flag byte
or BYTE PTR [bx],01000000b	; CapsLock on
```

> This code only runs in Real-address mode, and it does not work under Windows NT, 2000, or XP.

* Task: Jump to a label if an integer is even.
* Solution: AND the lowest bit with a 1. If the result is Zero, the number was even.

```assembly
mov ax,wordVal
and ax,1	; low bit set?
jz  EvenValue	; jump if Zero flag set
```

> JZ (jump if Zero) is covered in Section 6.3.

* Task: Jump to a label if the value in AL is not zero.
* Solution: OR the byte with itself, then use the JNZ (jump if not zero) instruction.

```assembly
or  al,al
jnz IsNotZero	; jump if not zero
```

### TEST Instruction

* Performs a **nondestructive** AND operation between each pair of matching bits in two operands
* No operands are modified, but the Zero flag is affected.
* Example: jump to a label if either bit 0 or bit 1 in AL is set.

```assembly
test al,00000011b
jnz  ValueFound
```

* Example: jump to a label if neither bit 0 nor bit 1 in AL is set.

```assembly
test al,00000011b
jz   ValueNotFound
```

### CMP Instruction

* Compares the **destination** operand to the **source** operand

  * **Nondestructive** subtraction of **source** from **destination** (destination operand is **not** changed)

* Syntax: CMP destination, source

* Example: destination == source

  ```assembly
  mov al,5
  cmp al,5	; Zero flag set
  ```

* Example: destination < source

  ```assembly
  mov al,4
  cmp al,5	; Carry flag set
  ```

* Example: destination > source

  ```assembly
  mov al,6
  cmp al,5	; ZF = 0, CF = 0
  ```

  (both the Zero and Carry flags are clear)

| **CMP Results**      | **ZF (ZR)** | **CF (CY)** |
| -------------------- | ----------- | ----------- |
| Destination < Source | 0           | 1           |
| Destination > Source | 0           | 0           |
| Destination = Source | 1           | 0           |

The comparisons shown here are performed with signed integers.

| **CMP Results**                | **SF (PL)** | **OF (OV)** | **Destination** | **Source** |
| ------------------------------ | ----------- | ----------- | --------------- | ---------- |
| Destination < Source (SF !=OF) | 0           | 1           | -2              | 127        |
| 1                              | 0           | -2          | 1               |            |
| Destination > Source (SF ==OF) | 0           | 0           | 127             | 1          |
| 1                              | 1           | 127         | -1              |            |

Destination = Source: ZF = 1

The comparisons shown here with signed integers.

* Example: destination > source

  ```assembly
  mov al,5
  cmp al,-5     ; Sign flag(0) == Overflow flag(0)
  ```

  ```assembly
  mov al, 120
  cmp al, -10
  ```

  ```assembly
  mov al, 120
  cmp al, 10
  ```

* Example: destination < source

  ```assembly
  mov al,-1
  cmp al,5      ; Sign flag(1) != Overflow flag(0)
  ```

  ```assembly
  mov al,-120
  cmp al,10     ; Sign flag(0) != Overflow flag(1) 
  ```

### Set and Clear Flags

* Set Zero flag

  ```assembly
  test al, 0
  ```

  * Clear Zero flag

    ```assembly
    or al, 1
    ```

* Set Sign flag

  ```assembly
  or al, 80h
  ```

* Clear Sign flag

  ```assembly
  and al, 7Fh
  ```

* Set Carry flag

  ```assembly
  stc
  ```

* Clear Carry flag

  ```assembly
  clc
  ```

* Set Overflow flag

  ```assembly
  mov al, 7Fh
  inc al		; SF = 1 ZF = 0 AF = 1 PF = 0
  ```

* Clear Overflow flag

  ```assembly
  or eax, 0
  ```

### Boolean Instructions in 64-Bit Mode

* 64-bit boolean **instructions**, for the most part, work **the same** as 32-bit instructions
* If the **source** operand is a constant whose size is **less** than **32** bits and the destination is the **lower** part of a **64-bit** register or memory operand, all **bits** in the **destination** operand are **affected**
* When the source is a **32-bit** constant or register, only the lower 32 **bits** of the destination operand are affected

## Conditional Jumps

* Jumps Based On . . .
  * Specific **flags**
  * **Equality**
  * **Unsigned comparisons**
  * **Signed** Comparisons
* Applications
* Encrypting a String
* Bit Test (BT) Instruction

### $J_{cond}$ Instruction

* A **conditional jump** instruction branches to a label when specific **register** or flag conditions are **met**
* Specific jumps:
  * **JB, JC** - jump to a label if the **Carry** flag is set
  * **JE, JZ** - jump to a label if the **Zero** flag is set
  * **JS** - jump to a label if the **Sign** flag is set
  * **JNE, JNZ** - jump to a label if the **Zero** flag is **clear**
  * **JECXZ** - jump to a label if **ECX** = 0

### $J_{cond}$ Ranges

* x86 processors:
  * 32-bit offset permits jump anywhere in memory

```output
Offset		Encoding					ASM Source
0040101A 	B0 80      mov al,80h 	      L1:  mov al, -128
0040101C 	3C 0A 	   cmp  al,0Ah 		 cmp al, 10
0040101E 	74 FA       je     L1 (40101Ah) 	 jz L1
00401020 	8A D8      mov bl,al 		 mov bl, al
```

```output
FA: -6			00401020
		     +  FFFFFFFA
		     ------------
			    0040101A
```

### Jumps Based on Specific Flags

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304090029651.png" alt="image-20220304090029651" style="zoom:67%;" />

### Jumps Based on Equality

<img src="D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220304090050832.png" alt="image-20220304090050832" style="zoom:67%;" />

### Jumps Based on Unsigned Comparisons

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304090114519.png" alt="image-20220304090114519" style="zoom:67%;" />

### Jumps Based on Signed Comparisons

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304090133817.png" alt="image-20220304090133817" style="zoom:67%;" />

### Applications

* Task: Jump to a label if unsigned EAX is greater than EBX

* Solution: Use CMP, followed by JA

  ```assembly
  cmp eax,ebx
  ja  Larger
  ```

* Task: Jump to a label if signed EAX is greater than EBX

* Solution: Use CMP, followed by JG

  ```assembly
  cmp eax,ebx
  jg  Greater
  ```

* Jump to label L1 if unsigned EAX is less than or equal to Val1

  ```assembly
  cmp eax,Val1
  jbe L1	; below or equal
  ```

* Jump to label L1 if signed EAX is less than or equal to Val1

  ```assembly
  cmp eax,Val1
  jle L1
  ```

* Compare unsigned AX to BX, and copy the larger of the two into a variable named Large

  ```assembly
  mov Large,bx
  cmp ax,bx
  jna Next
  mov Large,ax
  Next:
  ```

* Compare signed AX to BX, and copy the smaller of the two into a variable named Small

  ```assembly
  mov Small,ax
  cmp bx,ax
  jnl Next
  mov Small,bx
  Next:
  ```

* Jump to label L1 if the memory word pointed to by ESI equals Zero

  ```assembly
  cmp WORD PTR [esi],0
  je  L1
  ```

* Jump to label L2 if the doubleword in memory pointed to by EDI is even

  ```assembly
  test DWORD PTR [edi],1
  jz   L2
  ```

* Task: Jump to label L1 if bits 0, 1, and 3 in AL are all set.

* Solution: Clear all bits except bits 0, 1,and 3. Then compare the result with 00001011 binary.

  ```assembly
  and al,00001011b	; clear unwanted bits
  cmp al,00001011b	; check remaining bits
  je  L1	; all set? jump to L1
  ```

* Task: Jump to label L1 if **any** of bits 0, 1, or 3 in AL are set.

  ```assembly
  test al,00001011b	; check bits
  jnz L1	; any set? jump to L1
  ```

### BT (Bit Test) Instruction, (Optional)

* Copies bit n from an operand into the Carry flag

* Syntax: BT bitBase, n

  * bitBase may be r/m16 or r/m32
  * n may be r16, r32, or imm8

* Example: jump to label L1 if bit 9 is set in AX:

  ```assembly
  bt AX,9	; CF = bit 9
  jc L1	; jump if Carry
  ```

* BTC, BTR, BTS: (Complement, Reset, Set)

  ```assembly
  .data
  Semaphore WORD 10001000b
  .code
  btc Semaphore, 6  ; CF=0, Semaphore WORD 11001000b
  ```

## Conditional Loop Instructions

* LOOPZ and LOOPE
* LOOPNZ and LOOPNE

### LOOPZ and LOOPE

* Syntax: 

  ```assembly
  LOOPE destination
  LOOPZ destination
  ```

* Logic: 

  * ECX <- ECX – 1
  * if ECX > 0 and ZF=1, jump to destination

> In 32-bit mode, ECX is the loop counter register. In 16-bit real-address mode, CX is the counter, and in 64-bit mode, RCX is the counter.

### LOOPNZ and LOOPNE

* LOOPNZ (LOOPNE) is a conditional loop instruction

* Syntax: 

  ```assembly
  LOOPNZ destination
  LOOPNE destination
  ```

* Logic: 

* ECX <- ECX – 1; 

* if ECX > 0 and ZF=0, jump to destination

### LOOPNZ Example

The following code finds the first positive value in an array:

```assembly
.data
array SWORD -3,-6,-1,-10,10,30,40,4
sentinel SWORD 0				; How to simplify?
.code
mov esi,OFFSET array
mov ecx,LENGTHOF array
next:
test WORD PTR [esi],8000h	; test sign bit
pushfd					   ; push flags on stack
add esi,TYPE array
Popfd                    	; pop flags from stack
loopnz next              	; continue loop
jnz quit                 	; none found; 
sub esi,TYPE array       	; ESI points to value
quit:
; If the loop fails to find a
; positive number, it stops 
; when ECX equals zero.
```

## Conditional Structures

* Block-Structured IF Statements
* Compound Expressions with AND
* Compound Expressions with OR
* WHILE Loops
* Table-Driven Selection

### Block-Structured IF Statements

Assembly language programmers can easily translate logical statements written in C++/Java into assembly language. For example:

```cpp
if( op1 == op2 )
  X = 1;
else
  X = 2;
```

```assembly
mov eax,op1
cmp eax,op2
jne L1
mov X,1
jmp L2
L1:	mov X,2
L2:
```

### Compound Expression with AND

* When implementing the logical AND operator, consider that HLLs use **short-circuit** evaluation

* In the following example, if the **first** expression is **false**, the second expression is skipped:

  ```pseudocode
  if (al > bl) AND (bl > cl)
    X = 1;
  ```

  This is one possible implementation . . .

  ```assembly
  	cmp al,bl	; first expression...
  	ja  L1
  	jmp next
  L1:
  	cmp bl,cl	; second expression...
  	ja  L2
  	jmp next
  L2:				; both are true
  	mov X,1		; set X to 1
  next:
  ```

  > But the following implementation uses  29% less code by reversing the first relational operator. We allow the program to "fall through" to the second expression:

  ```assembly
  	cmp al,bl	; first expression...
  	jbe next	; quit if false
  	cmp bl,cl	; second expression...
  	jbe next	; quit if false
  	mov X,1		; both are true
  next:
  ```

* ​    Some non-short-circuit evaluation (e.g., early BASIC)

### Compound Expression with OR

* When implementing the logical OR operator, consider that HLLs use **short-circuit** evaluation

* In the following example, if the first expression is **true**, the second expression is **skipped**:

  ```pseudocode
  if (al > bl) OR (bl > cl)
    X = 1;
  ```

  We can use "fall-through" logic to keep the code as short as possible:

  ```assembly
  	cmp al,bl	; is AL > BL?
  	ja  L1		; yes
  	cmp bl,cl	; no: is BL > CL?
  	jbe next	; no: skip next statement
  L1:	mov X,1		; set X to 1
  next:
  ```

### WHILE Loops

A **WHILE** loop is really an **IF** statement followed by the **body** of the **loop**, followed by an **unconditional jump** to the top of the **loop**. Consider the following example:

```pseudocode
while( eax < ebx)
	eax = eax + 1;
```

This is a possible implementation:

```assembly
top:	cmp eax,ebx	; check loop condition
	jae next		; false? exit loop
	inc eax			; body of loop
	jmp top			; repeat the loop
next:
```

### Table-Driven Selection

* Table-driven selection uses a table lookup to replace a multiway selection structure
* Create a table containing lookup values and the offsets of labels or procedures
* Use a loop to search the table
* Suited to a large number of comparisons

| **Lookup** | **Procedure** |
| ---------- | ------------- |
| ‘A’        | Process_A     |
| ‘B’        | Process_B     |
| ‘C’        | Process_C     |
| ‘D’        | Process_D     |
| …          | …             |

Step 1: create a table containing lookup values and procedure offsets:

```assembly
.data
CaseTable BYTE 'A'	; lookup value
	DWORD Process_A	; address of procedure
	EntrySize = ($ - CaseTable)
	BYTE 'B'
	DWORD Process_B
	BYTE 'C'
	DWORD Process_C
	BYTE 'D'
	DWORD Process_D

NumberOfEntries = ($ - CaseTable) / EntrySize
```

Table of Procedure Offsets:

![image-20220304091801808](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220304091801808.png)

Step 2: Use a loop to search the table. When a match is found, call the procedure offset stored in the current table entry:

```assembly
	mov ebx,OFFSET CaseTable	; point EBX to the table
	mov ecx,NumberOfEntries		; loop counter

L1:	cmp al,[ebx]				; match found?
	jne L2						; no: continue
	; required for procedure pointers
	call NEAR PTR [ebx + 1]		; yes: call the procedure
	call WriteString			; display message
	call Crlf
	jmp L3						; and exit the loop
L2:	add ebx,EntrySize			; point to next entry
	loop L1						; repeat until ECX = 0

L3:
```

## Application: Finite-State Machines

* A finite-state machine (**FSM**) is a **graph** structure that **changes** state based on some **input**. Also called a **state-transition** diagram.
* We use a **graph** to represent an **FSM**, with squares or circles called **nodes**, and lines with **arrows** between the **circles** called **edges**.

* A **FSM** is a **specific instance** of a more general **structure** called a ***directed graph***.
* Three basic states, represented by nodes:
  * **Start** state
  * **Terminal** state(s)
  * **Nonterminal** state(s)

* Accepts any sequence of **symbols** that puts it into an **accepting** (**final**) state
* Can be used to **recognize**, or **validate** a sequence of characters that is **governed** by language rules (called a **regular** expression)
* Advantages:
  * Provides **visual** tracking of **program's** flow of control
  * **Easy** to modify
  * Easily **implemented** in assembly language

* FSM that recognizes strings beginning with 'x', followed by letters 'a'..'y', ending with 'z':

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304092339331.png" alt="image-20220304092339331" style="zoom:67%;" />

  1. from state A to state B can only be accomplished if the letter x is read from the input stream. 
  2. from state B to itself is accomplished by the input of any letter of the alphabet except z.
  3. A transition from state B to state C occurs only when the letter z is read from the input stream.

* FSM that recognizes signed integers:

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304092349322.png" alt="image-20220304092349322" style="zoom:67%;" />

  * [+|-]d…dd

### Implementing an FSM

The following is code from State A in the Integer FSM:

```assembly
StateA:
	call Getnext			; read next char into AL
	cmp al,'+'				; leading + sign?
	je StateB				; go to State B
	cmp al,'-'				; leading - sign?
	je StateB				; go to State B
	call IsDigit			; ZF = 1 if AL = digit
	jz StateC				; go to State C
	call DisplayErrorMsg	 ; invalid input found
	jmp Quit
```

View the Finite.asm source code.

### Flowchart of State A

State A accepts a plus or minus sign, or a decimal digit.

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304092537667.png" alt="image-20220304092537667" style="zoom:67%;" />

## Creating IF Statements

* Runtime Expressions
* Relational and Logical Operators
* MASM-Generated Code
* .REPEAT Directive
* .WHILE Directive

### Runtime Expressions

* .IF, .ELSE, .ELSEIF, and .ENDIF can be used to evaluate runtime expressions and create

* block-structured IF statements.

* Examples:

  ```assembly
  .IF eax > ebx
  	mov edx,1
  .ELSE
  	mov edx,2
  .ENDIF
  ```

  ```assembly
  .IF eax > ebx && eax > ecx
  	mov edx,1
  .ELSE
  	mov edx,2
  .ENDIF
  ```

* MASM generates "hidden" code for you, consisting of code labels, CMP and conditional jump instructions.

### Relational and Logical Operators

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220304092755913.png" alt="image-20220304092755913" style="zoom:67%;" />

### Signed and Unsigned Comparisons

```assembly
.data
val1   DWORD 5
result DWORD ?
.code
mov eax,6
.IF eax > val1
  mov result,1
.ENDIF
```

Generated code:

```assembly
	mov eax,6
	cmp eax,val1
	jbe @C0001 
	mov result,1
@C0001:
```

> MASM automatically generates an unsigned jump (JBE) because val1 is unsigned.

```assembly
.data
val1   SDWORD 5
result SDWORD ?
.code
mov eax,6
.IF eax > val1
  mov result,1
.ENDIF
```

Generated code:

```assembly
	mov eax,6
	cmp eax,val1
	jle @C0001 
	mov result,1
@C0001:
```

> MASM automatically generates a signed jump (JLE) because val1 is signed.

```assembly
.data
result DWORD ?
.code
mov ebx,5
mov eax,6
.IF eax > ebx
  mov result,1
.ENDIF
```

Generated code:

```assembly
	mov ebx,5
	mov eax,6
	cmp eax,ebx
	jbe @C0001 
	mov result,1
@C0001:
```

> MASM automatically generates an unsigned jump (JBE) when both operands are registers ...

```assembly
.data
result SDWORD ?
.code
mov ebx,5
mov eax,6
.IF SDWORD PTR eax > ebx
  mov result,1
.ENDIF
```

Generated code:

```assembly
	mov ebx,5
	mov eax,6
	cmp eax,ebx
	jle @C0001 
	mov result,1
@C0001:
```

... unless you prefix one of the register operands with the SDWORD PTR operator. Then a signed jump is generated.

### .REPEAT Directive

**Executes** the loop body **before** testing the loop **condition** associated with the .**UNTIL** directive. 
Example:

```assembly
; Display integers 1 – 10:

mov eax,0
.REPEAT
	inc eax
	call WriteDec
	call Crlf
.UNTIL eax == 10
```

### .WHILE Directive

**Tests** the loop **condition** before **executing** the loop **body** The .**ENDW** directive marks the end of the loop. 
Example:

```assembly
; Display integers 1 – 10:

mov eax,0
.WHILE eax < 10
	inc eax
	call WriteDec
	call Crlf
.ENDW
```

### MASM-Generated Code

```pseudocode
mov eax, 0
.while eax <10
	inc eax
.endw
```

```output
00000026  B8 00000000		mov eax, 0
							.while eax <10
0000002B  EB 01	   *	jmp    @C0001
0000002D		       *@C0002:
0000002D  40			    inc eax
						      .endw
0000002E		       *@C0001:
0000002E  83 F8 0A	   *	 cmp    eax, 00Ah
00000031  72 FA	   *	 jb	    @C0002
```

## Summary

* Bitwise instructions (AND, OR, XOR, NOT, TEST) 
  * manipulate individual bits in operands
* CMP – compares operands using implied subtraction
  * sets condition flags
* Conditional Jumps & Loops
  * equality: JE, JNE
  * flag values: JC, JZ, JNC, JP, ...
  * signed: JG, JL, JNG, ...
  * unsigned: JA, JB, JNA, ...
  * LOOPZ, LOOPNZ, LOOPE, LOOPNE
* Flowcharts – logic diagramming tool
* Finite-state machine – tracks state changes at runtime

# Integer Arithmetic

* Shift and Rotate Instructions
* Shift and Rotate Applications
* Multiplication and Division Instructions
* Extended Addition and Subtraction
* ASCII and Unpacked Decimal Arithmetic
* Packed Decimal Arithmetic

## Shift and Rotate Instructions

* Logical Shift
* SHL Instruction 
* SHR Instruction 
* SAL and SAR Instructions 
* ROL Instruction 
* ROR Instruction 
* RCL and RCR Instructions 
* SHLD/SHRD Instructions

### Logical Shift

* A logical shift fills the newly created bit position with zero:

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318083917874.png" alt="image-20220318083917874" style="zoom:67%;" />

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318083938161.png" alt="image-20220318083938161" style="zoom:67%;" />

### Arithmetic Shift

* An arithmetic shift fills the newly created bit position with a copy of the number's sign bit:

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318083951763.png" alt="image-20220318083951763" style="zoom:67%;" />

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318083959699.png" alt="image-20220318083959699" style="zoom:67%;" />

### SHL Instruction

* The SHL (shift left) instruction performs a logical left shift on the destination operand, filling the lowest bit with 0.

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318084016402.png" alt="image-20220318084016402" style="zoom:67%;" />

* Operand types for SHL:

  ```assembly
  SHL reg,imm8
  		SHL mem,imm8
  		SHL reg,CL
  		SHL mem,CL
  		; (Same for all shift and rotate instructions)
  
  ```

### Fast Multiplication

Shifting left 1 bit multiplies a number by 2

```assembly
mov dl,5
shl dl,1
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318084127473.png" alt="image-20220318084127473" style="zoom:67%;" />

Shifting ==left n== bits ==multiplies== the operand by ==2^n^==
For example, 5 * 2^2^ = 20

```assembly
mov dl,5
shl dl,2	; DL = 20
```

### SHR Instruction

The SHR (shift ==right==) instruction performs a ==logical== right shift on the destination operand. The highest bit position is filled with a ==zero==.

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318084351116.png" alt="image-20220318084351116" style="zoom:67%;" />

```assembly
mov dl,80
shr dl,1	; DL = 40
shr dl,2	; DL = 10
```

> Q: How about 81 shr 1? 
> 40

### SAL and SAR Instructions

SAL (==shift arithmetic left==) is identical to SHL.
SAR (==shift arithmetic right==) performs a ==right== arithmetic shift on the destination operand.

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318084539568.png" alt="image-20220318084539568" style="zoom:67%;" />

An arithmetic shift **preserves** the number's **sign**.

```assembly
mov dl,-80	; 10110000
sar dl,1	; DL = -40, 11011000b
sar dl,2	; DL = -10, 11110110b
```

> Q: How about -81 sar 1? (1010 1111) 
> -41 (1101 0111) 

### ROL Instruction

* ROL (**rotate**) shifts each bit to the left
* The **highest** bit is copied into both the **Carry** flag and into the lowest bit
* No bits are lost

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318084918579.png" alt="image-20220318084918579" style="zoom:67%;" />

```assembly
mov al,11110000b
rol al,1	; AL = 11100001b

mov dl,3Fh
rol dl,4	; DL = F3h
```

### ROR Instruction

* ROR (rotate right) shifts each bit to the right
* The lowest bit is copied into both the Carry flag and into the highest bit
* No bits are lost

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318085052282.png" alt="image-20220318085052282" style="zoom:67%;" />

```assembly
mov al,11110000b
ror al,1	; AL = 01111000b

mov dl,3Fh
ror dl,4	; DL = F3h
```

### RCL Instruction

* RCL (**rotate carry** left) shifts each bit to the left
* Copies the **Carry** flag to the least significant bit
* Copies the **most** significant bit to the **Carry** flag

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318085335721.png" alt="image-20220318085335721" style="zoom:67%;" />

```assembly
clc		; CF = 0
mov bl,88h		; CF,BL = 0 10001000b
rcl bl,1		; CF,BL = 1 00010000b
rcl bl,1		; CF,BL = 0 00100001b
```

### RCR Instruction

* RCR (**rotate carry right**) shifts each bit to the right
* Copies the **Carry** flag to the **most** significant bit
* Copies the **least** significant bit to the **Carry** flag

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318085437546.png" alt="image-20220318085437546" style="zoom:67%;" />

```assembly
stc	; CF = 1
mov ah,10h	; CF,AH = 1 00010000b
rcr ah,1	; CF,AH = 0 10001000b
```

### SHLD Instruction

* Shifts a destination operand a given number of bits to the left 

* The bit positions opened up by the shift are filled by the most significant bits of the source operand

* The source operand is not affected

* Syntax:

  ```assembly
  SHLD destination, source, count
  ```

  Operand types:

  ```assembly
  SHLD reg16/32, reg16/32, imm8/CL
  SHLD mem16/32, reg16/32, imm8/CL
  ```

### SHLD Example

Shift count of 1:

```assembly
mov al,11100000b
mov bl,10011101b
shld al,bl,1
```

![image-20220318085623156](D:\LakeheadUCourse\2nd_year_winter\AssemblyLang_COMP2476\statics\image-20220318085623156.png)

### SHRD Instruction

* Shifts a destination operand a given number of bits to the right

* The bit positions opened up by the shift are filled by the least significant bits of the source operand

* The source operand is not affected

* Syntax:

  ```assembly
  SHRD destination, source, count
  ```

  Operand types:

  ```assembly
  SHRD reg16/32, reg16/32, imm8/CL
  SHRD mem16/32, reg16/32, imm8/CL
  ```

### SHRD Example

Shift count of 1:

```assembly
mov al,11000001b
mov bl,00011101b
shrd al,bl,1
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318085745762.png" alt="image-20220318085745762" style="zoom:67%;" />

## Shift and Rotate Applications

* Shifting Multiple Doublewords 
* Binary Multiplication 
* Displaying Binary Bits 
* Isolating a Bit String 

### Shifting Multiple Doublewords

* Programs sometimes need to **shift** all bits **within** an **array**
* The following shifts an array of 3 **doublewords** 1 bit to the right

```assembly
.data
ArraySize = 3
array DWORD ArraySize DUP(99999999h)      ; 1001 1001...
.code
mov esi,0
shr array[esi + 8],1	; high dword
rcr array[esi + 4],1	; middle dword, include Carry
rcr array[esi],1		; low dword, include Carry
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318085946475.png" alt="image-20220318085946475" style="zoom:67%;" />

```output
23456789 23456789 23456789
--------------------------
11A2B3C4 91A2B3C4 91A2B3C4
```

### Binary Multiplication

multiply 123 * 36

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318090039365.png" alt="image-20220318090039365" style="zoom:67%;" />

* We already know that ==SHL== performs unsigned ==multiplication== efficiently when the multiplier is a **power** of 2. 
* You can factor any **binary** number into **powers** of 2. 
  * For example, to ==multiply== EAX * 36, factor 36 into 32 + 4 and use the **distributive** property of **multiplication** to **carry** out the operation:

```pseudocode
EAX * 36 
= EAX * (32 + 4)
= (EAX * 32)+(EAX * 4)
```

```assembly
mov eax,123
mov ebx,eax
shl eax,5	; mult by 25
shl ebx,2	; mult by 22
add eax,ebx
```

### Displaying Binary Bits

Algorithm: Shift ==MSB== into the ==Carry== flag; If CF = 1, append a "1" character to a **string**; otherwise, append a "**0**" character. Repeat in a loop, 32 times.

```assembly
; Ref: WriteBinB in Irvine32.asm 
.data
buffer BYTE 32 DUP(0),0
.code
	mov ecx,32
	mov esi,OFFSET buffer
L1:	shl eax,1
	mov BYTE PTR [esi],'0'
	jnc L2
	mov BYTE PTR [esi],'1'
L2:	inc esi
	loop L1
```

### Isolating a Bit String

The ==MS-DOS== file date field packs the year, month, and day into 16 bits: year is relative to 1980

* 1999/03/10

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318090645437.png" alt="image-20220318090645437" style="zoom:67%;" />

Isolate the Month field:

```assembly
mov ax,dx	; make a copy of DX
shr ax,5	; shift right 5 bits
and al,00001111b	; clear bits 4-7
mov month,al		; save in month variable
```

### DOS File Time Fields

Time stamp field:

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318090814977.png" alt="image-20220318090814977" style="zoom:67%;" />

## Shift and Rotate Applications

* MUL Instruction 
* IMUL Instruction 
* DIV Instruction 
* Signed Integer Division
* CBW, CWD, CDQ Instructions
* IDIV Instruction 
* Implementing Arithmetic Expressions 

### MUL Instruction

* In 32-bit mode, MUL (unsigned multiply) instruction multiplies an 8-, 16-, or 32-bit operand by either AL, AX, or EAX.

* The instruction formats are:

  ```assembly
  MUL r/m8
  MUL r/m16
  MUL r/m32
  ```

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318091057167.png" alt="image-20220318091057167" style="zoom:67%;" />

### 64-Bit MUL Instruction

* In 64-bit mode, MUL (unsigned multiply) instruction multiplies a 64-bit operand by RAX, producing a 128-bit product.

* The instruction formats are:

  ```assembly
  MUL r/m64
  ```

  Example:

  ```assembly
  mov rax,0FFFF0000FFFF0000h
  mov rbx,2
  mul rbx 	; RDX:RAX = 0000000000000001FFFE0001FFFE0000
  ```

### MUL Examples

100h * 2000h, using 16-bit operands:

> The Carry flag indicates whether or not the upper half of the product contains significant digits.

```assembly
.data
val1 WORD 2000h
val2 WORD 100h
.code
mov ax,val1
mul val2	; DX:AX = 00200000h, CF=1
```

12345h * 1000h, using 32-bit operands:

```assembly
mov eax,12345h
mov ebx,1000h
mul ebx	; EDX:EAX = 0000000012345000h, CF=0
```

### IMUL Instruction

* IMUL (signed integer multiply ) multiplies an 8-, 16-, or 32-bit signed operand by either AL, AX, or EAX
* Preserves the sign of the product by ==sign-extending== it into the upper half of the destination register

Example: multiply 48 * 4, using 8-bit operands:

```assembly
mov  al,48
mov  bl,4
imul bl	; AX = 00C0h, OF=1
; OF=1 because AH is not a sign extension of AL.
```

### IMUL Examples

Multiply 4,823,424 *  -423:

```assembly
mov eax,4823424
mov ebx,-423
imul ebx	; EDX:EAX = FFFFFFFF86635D80h, OF=0
; OF=0 because EDX is a sign extension of EAX.
```

### DIV Instruction

* The DIV (unsigned divide) instruction performs 8-bit, 16-bit, and 32-bit division on unsigned integers
  A single operand is supplied (register or memory operand), which is assumed to be the divisor 
  Instruction formats:

  ```assembly
  DIV reg/mem8
  DIV reg/mem16
  DIV reg/mem32
  ```

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318092141106.png" alt="image-20220318092141106" style="zoom:67%;" />

### DIV Examples

Divide 8003h by 100h, using 16-bit operands:

```assembly
mov dx,0		; clear dividend, high
mov ax,8003h	; dividend, low
mov cx,100h		; divisor
div cx			; AX = 0080h, DX = 3
```

Same division, using 32-bit operands:

```assembly
mov edx,0		; clear dividend, high
mov eax,8003h	; dividend, low
mov ecx,100h	; divisor
div ecx			; EAX = 00000080h, EDX = 3
```

### 64-Bit DIV Example

Divide 000001080000000033300020h by 00010000h:

```assembly
.data
dividend_hi QWORD 00000108h
dividend_lo QWORD 33300020h
divisor QWORD 00010000h

.code
mov rdx, dividend_hi
mov rax, dividend_lo
div divisor 		; RAX = quotient
				   ; RDX = remainder

; RAX (quotient):  0108000000003330h 
; RDX (remainder): 0000000000000020h

```

### Signed Integer Division (IDIV)

* **Signed** integers must be **sign-extended** before **division** takes place
  * fill **high** byte/word/doubleword with a copy of the **low** byte/word/doubleword's sign bit
* For example, the high byte contains a copy of the sign bit from the low byte:

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318092336715.png" alt="image-20220318092336715" style="zoom:67%;" />

### CBW, CWD, CDQ Instructions

* The CBW, CWD, and CDQ instructions provide important sign-extension operations:

  * CBW (convert **byte** to word) extends AL into AH
  * CWD (convert **word** to doubleword) extends AX into DX
  * CDQ (convert **doubleword** to quadword) extends EAX into EDX

* Example: 

  ```assembly
  .data
  dwordVal SDWORD -101 	; FFFFFF9Bh
  .code
  mov eax,dwordVal
  cdq 					; EDX:EAX = FFFFFFFFFFFFFF9Bh
  ```

### IDIV Instruction

* IDIV (signed divide) performs signed integer division
  Same syntax and operands as DIV instruction

Example: 8-bit division of –48 by 5

```assembly
mov  al,-48
cbw		; extend AL into AH
mov  bl,5
idiv bl	; AL = -9,  AH = -3
```

* The remainder always has the **same** sign as the **dividend**

* All arithmetic **status** flags **undefined** after DIV and IDIV

* if this

  ```assembly
  mov bl, -5       ; AL = 9, AH = -3
  ```

### IDIV Examples

Example: 16-bit division of –48 by 5

```assembly
mov  ax,-48
cwd		; extend AX into DX
mov  bx,5	
idiv bx	; AX = -9,  DX = -3
```

Example: 32-bit division of –48 by 5

```assembly
mov  eax,-48
cdq		; extend EAX into EDX
mov  ebx,5
idiv ebx	; EAX = -9,  EDX = -3
```

### Unsigned Arithmetic Expressions

* Some good reasons to learn how to implement integer expressions:
  * **Learn** how do compilers do it
  * **Test** your **understanding** of MUL, IMUL, DIV, IDIV
  * **Check** for overflow (Carry and Overflow flags)

Example:   var4 = (var1 + var2) * var3

```assembly
; Assume unsigned operands
mov  eax,var1
add  eax,var2	; EAX = var1 + var2
mul  var3		; EAX = EAX * var3
jc   TooBig		; check for carry
mov  var4,eax	; save product
```

### Signed Arithmetic Expressions

Example:   eax = (-var1 * var2) + var3

```assembly
mov  eax,var1
neg  eax
imul var2
jo   TooBig	; check for overflow
add  eax,var3
jo   TooBig	; check for overflow
```

Example:   var4 = (var1 * 5) / (var2 – 3)

```assembly
mov  eax,var1 	; left side
mov  ebx,5
imul ebx 		; EDX:EAX = product
mov  ebx,var2 	; right side
sub  ebx,3
idiv ebx 		; EAX = quotient
mov  var4,eax
```

Example:   var4 = (var1 * -5) / (-var2 % var3);

```assembly
mov  eax,var2	; begin right side
neg  eax
cdq 			; sign-extend dividend
idiv var3 		; EDX = remainder
mov  ebx,edx 	; EBX = right side
mov  eax,-5 	; begin left side
imul var1 		; EDX:EAX = left side
idiv ebx 		; final division
mov  var4,eax 	; quotient
```

## Extended Addition and Subtraction

* ADC Instruction 

* Extended Precision Addition

* SBB Instruction

* Extended Precision Subtraction

  > The instructions in this section do not apply to 64-bit mode programming.

### Extended Precision Addition

* Adding two operands that are longer than the computer's word size (32 bits).
  * Virtually no limit to the size of the operands
* The arithmetic must be performed in steps
  * The Carry value from each step is **passed** on to the next step.

### ADC Instruction

* ADC (add with carry) instruction adds both a source operand and the contents of the Carry flag to a destination operand.

* Operands are binary values

  * Same syntax as ADD, SUB, etc.

* Example

  * Add two 32-bit integers (FFFFFFFFh + FFFFFFFFh), producing a 64-bit sum in EDX:EAX:

    ```assembly
    mov edx,0
    mov eax,0FFFFFFFFh
    add eax,0FFFFFFFFh
    adc edx,0	;EDX:EAX = 00000001FFFFFFFEh
    ```

### Extended Addition Example

* Task: Add 1 to EDX:EAX
  * Starting value of EDX:EAX: 00000000FFFFFFFFh
  * Add the lower 32 bits first, setting the Carry flag. 
  * Add the upper 32 bits, and include the Carry flag.

```assembly
mov edx,0	; set upper half
mov eax,0FFFFFFFFh	; set lower half
add eax,1 	; add lower half
adc edx,0 	; add upper half

; EDX:EAX = 00000001 00000000
```

### SBB Instruction

* The SBB (**subtract** with borrow) instruction subtracts both a source operand and the value of the **Carry** flag from a **destination** operand.
* Operand syntax:
  * Same as for the ADC instruction

### Extended Subtraction Example

* Task: Subtract 1 from EDX:EAX
  * Starting value of EDX:EAX: 0000000100000000h 
  * Subtract the lower 32 bits first, setting the Carry flag. 
  * Subtract the upper 32 bits, and include the Carry flag.

```assembly
mov edx,1 	; set upper half
mov eax,0 	; set lower half
sub eax,1 	; subtract lower half
sbb edx,0 	; subtract upper half

; EDX:EAX = 00000000 FFFFFFFF
```

## ASCII and Unpacked Decimal Arithmetic

### Binary-Coded Decimal

* Binary-coded decimal (BCD) integers use 4 binary bits to represent each decimal digit
* A number using ==unpacked BCD== representation stores a decimal digit in the lower four bits of each byte
  * For example, 5,678 is stored as the following sequence of hexadecimal bytes:

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318093435108.png" alt="image-20220318093435108" style="zoom:50%;" />

### ASCII Decimal

* A number using **ASCII Decimal** representation stores a single ASCII digit in each byte

* The high 4 bits of an unpacked decimal integer are always zeros, whereas the same bits in an ASCII decimal number are equal to 0011b. In any case, both types of integers store one digit per byte.

  * For example, 5,678 is stored as the following sequence of hexadecimal bytes:

    <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318093628393.png" alt="image-20220318093628393" style="zoom:50%;" />

## Packed Decimal Arithmetic

* Packed decimal integers store two decimal digits per byte 

  * For example, 12,345,678 can be stored as the following sequence of hexadecimal bytes:

    <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220318093722077.png" alt="image-20220318093722077" style="zoom:50%;" />

  * Packed decimal is also known as ==packed BCD==.

  * Good for financial values – extended precision possible, without rounding errors.

### DAA Instruction

* The DAA (==decimal adjust after addition==) instruction converts the binary result of an ADD or ADC operation to packed decimal format.
  * The **value** to be adjusted must be in **AL**
  * If the **lower** digit is **adjusted**, the **Auxiliary** Carry flag is set.
  * If the **upper** digit is adjusted, the **Carry** flag is set.

### DAA Logic

> If AL = AL + 6 sets the Carry flag, its value is used when evaluating AL(hi).

```assembly
If (AL(lo) > 9) or (AuxCarry = 1)
  AL = AL + 6
  AuxCarry = 1
Else
  AuxCarry = 0
Endif

If (AL(hi) > 9) or Carry = 1
  AL = AL + 60h
  Carry = 1
Else
  Carry = 0
Endif
```

### DAA Examples

* Example: calculate BCD 35 + 48

  ```assembly
  mov al,35h
  add al,48h 	; AL = 7Dh, AC =0, CF =0, OF =0
  daa 		; AL = 83h, AC =1, CF =0 
  ```

* Example: calculate BCD 35 + 65

  ```assembly
  mov al,35h
  add al,65h 	; AL = 9Ah, AC =0, CF =0, OF =1
  daa 		; AL = 00h, AC =1, CF =1
  ```

* Example: calculate BCD 69 + 29

  ```assembly
  mov al,69h
  add al,29h 	; AL = 92h, AC =1, CF =0, OF =1
  daa 		; AL = 98h, AC =1, CF =0
  ```

### DAS Instruction

* The DAS (==decimal adjust after subtraction==) instruction converts the binary result of a SUB or SBB operation to packed decimal format.

* The value must be in AL

* Example: subtract BCD 48 from 85

  ```assembly
  mov al,85h
  mov bl,48h
  sub al,bl 	; AL = 3Dh, AC =1, CF =0, OF =1
  das 		; AL = 37h, AC =1, CF =0
  ```

### DAS Logic

> If AL = AL - 6 sets the Carry flag, its value is used when evaluating AL in the second IF statement.

```pseudocode
If (AL(lo) > 9) OR (AuxCarry = 1)
	AL = AL − 6;
	AuxCarry = 1;
Else
AuxCarry = 0;
Endif

If (AL > 9FH) or (Carry = 1)
	AL = AL − 60h;
	Carry = 1;
Else
	Carry = 0;
Endif
```

### DAS Examples

* Example: subtract BCD 48 – 35

  ```assembly
  mov al,48h
  sub al,35h 	; AL = 13h, AC =0, CF =0, OF =0
  das 		; AL = 13h, AC =0, CF =0
  ```

* Example: subtract BCD 62 – 35

  ```assembly
  mov al,62h
  sub al,35h 	; AL = 2Dh, AC =1, CF =0, OF =0
  das 		; AL = 27h, AC =1, CF =0
  ```

* Example: subtract BCD 12 – 29

  ```assembly
  mov al,12h
  sub al,29h 	; AL = E9h, AC =1, CF =1, OF =0
  das 		; AL = 83h, AC =1, CF =1
  ```

* Example: subtract BCD 32 – 39

  ```assembly
  mov al,32h
  sub al,39h 	; AL = F9h, AC =1, CF = 1
  das 		; AL = 93h, AC =1, CF = 1
  ```

  > Steps: 
  > AL = F9h
  > CF = 1, so subtract 6 from F9h
  > AL = F3h
  > F3h > 9Fh, so subtract 60h from F3h
  > AL = 93h, CF = 1

## Summary

* Shift and rotate instructions are some of the best tools of assembly language
  * finer control than in high-level languages
  * SHL, SHR, SAR, ROL, ROR, RCL, RCR
* MUL and DIV – integer operations
  * close relatives of SHL and SHR
  * CBW, CDQ, CWD: preparation for division
* 32-bit Mode only:
  * Extended precision arithmetic: ADC, SBB
  * Packed decimal operations (DAA, DAS)

# Advanced Procedures

## Overview

* Stack Frames
* Recursion
* INVOKE, ADDR, PROC, and PROTO
* Creating Multimodule Programs
* Advanced Use of Parameters (optional)
* Java Bytecodes (optional)

## Stack Frames

* Stack Parameters
* Local Variables
* ENTER and LEAVE Instructions
* LOCAL Directive
* WriteStackFrame Procedure

Stack Frame

* Also known as an activation record
* Area of the stack set aside for a procedure's return address, passed parameters, saved registers, and local variables
* Created by the following steps:
  * Calling program pushes arguments on the stack and calls the procedure.
  * The called procedure pushes EBP on the stack, and sets EBP to ESP.
  * If local variables are needed, a constant is subtracted from ESP to make room on the stack.

### Stack Parameters

* More convenient than register parameters

* Two possible ways of calling DumpMem

  ```assembly
  pushad
  mov esi,OFFSET array
  mov ecx,LENGTHOF array
  mov ebx,TYPE array
  call DumpMem
  popad
  ```

  ```assembly
  push TYPE array
  push LENGTHOF array
  push OFFSET array
  call DumpMem
  ```

* Why need Stack Parameters? 

* Anatomy of C code

  ```c
    int x = AddTwo(5, 6);
    int y = f(x, true);
  ```

  ```c
  int AddTwo(int i, int j)
  {
     return i+j;
  }
  
  int f(int &i, bool b)
  { 
     int n, m;  // do...
     return m;
  }
  ```

### Passing Arguments by Value

* Push argument values on stack
* Call the called-procedure
* Accept a return value in EAX, if any
* Remove arguments from the stack if the called-procedure did not remove them

#### Example

```assembly
.data
val1  DWORD 5
val2  DWORD 6

.code
push val2
push val1
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325084759101.png" alt="image-20220325084759101" style="zoom:67%;" />

### Passing Arguments by Value: AddTwo

```c
int n = AddTwo( 5, 6 );
```

```assembly
.data
sum DWORD ?
.code
	push 6 			; second argument
	push 5 			; first argument
	call AddTwo		; EAX = sum
	mov  sum,eax	; save the sum
```

```assembly
AddTwo PROC
	push ebp
	mov  ebp,esp
	.
	.
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325084842027.png" alt="image-20220325084842027" style="zoom:67%;" />

### Passing by Reference

* Push the offsets of arguments on the stack
* Call the procedure
* Accept a return value in EAX, if any
* Remove arguments from the stack if the called procedure did not remove them

#### Example

```assembly
.data
val1  DWORD 5
val2  DWORD 6

.code
push OFFSET val2
push OFFSET val1
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325084950422.png" alt="image-20220325084950422" style="zoom:67%;" />

### Stack after the CALL

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325085013634.png" alt="image-20220325085013634" style="zoom:67%;" />

### Passing Arguments by Reference: Swap

An argument passed by ==reference== consists of the ==address== (offset) of an object:

```assembly
push offset val2
push offset val1
call Swap
```

In C/C++, 

```c
Swap(&val1, &val2);
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325085059909.png" alt="image-20220325085059909" style="zoom:67%;" />

### Accessing Stack Parameters (C/C++)

* C and C++ functions access stack parameters using constant offsets from EBP^1^.
  * Example: [ebp + 8]
* EBP is called the base pointer or frame pointer because it holds the base address of the stack frame.
* EBP does ==not== change value during the function.
* EBP must be restored to its original value when a function returns.

## RET Instruction

* ==Return== from subroutine

* Pops stack into the ==instruction== pointer (EIP or IP). Control transfers to the ==target== address.

* Syntax:

  * ```assembly
    RET
    RET n
    ```

* Optional operand n causes n bytes to be added to the stack pointer after EIP (or IP) is ==assigned== a value.

### C Call : Caller releases stack

RET does not clean up the stack.

```assembly
AddTwo_C PROC
    push ebp
    mov  ebp,esp
    mov  eax,[ebp + 12]   	; second parameter
    add  eax,[ebp + 8]		; first parameter
    pop  ebp
    ret						; caller cleans up the stack
AddTwo_C ENDP
```

### STDCall : Procedure releases stack

The RET n instruction cleans up the stack.

```assembly
AddTwo PROC
    push ebp
    mov  ebp,esp
    mov  eax,[ebp + 12]   	; second parameter
    add  eax,[ebp + 8]		; first parameter
    pop  ebp
    ret  8					; clean up the stack
AddTwo ENDP

_Example2 PROC
	push 6
	push 5
	call AddTwo
	call DumpRegs			; sum is in EAX
	ret
_Example2 ENDP
```

## Passing an Array by Reference

* The ArrayFill procedure ==fills== an array with ==16-bit== random integers
* The calling program ==passes== the ==address== of the array, along with a count of the number of array elements:

```assembly
.data
count = 100
array WORD count DUP(?)
.code
	push OFFSET array
	push COUNT
	call ArrayFill
```

ArrayFill can reference an array without knowing the array's name:

```assembly
ArrayFill PROC
	push ebp
	mov  ebp,esp
	pushad
	mov  esi,[ebp+12]
	mov  ecx,[ebp+8]
	.
	.
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325085439078.png" alt="image-20220325085439078" style="zoom:67%;" />

ESI ==points== to the ==beginning== of the array, so it's easy to use a loop to access each array element. 

### ArrayFill Procedure

```assembly
ArrayFill PROC	
	push ebp
	mov  ebp,esp
	pushad				; save registers
	mov  esi,[ebp+12]	; offset of array, beginning
	mov  ecx,[ebp+8]	; array size
	cmp  ecx,0			; ECX == 0?
	je   L2				; yes: skip over loop

L1:	mov  eax,10000h		; get random 0 - FFFFh
	call RandomRange	; from the link library
	mov  [esi],ax
	add  esi,TYPE WORD
	loop L1

L2:	popad				; restore registers
	pop ebp
   ret 8				; clean up the stack
ArrayFill ENDP
```

## Local Variables

* Only ==statements== within ==subroutine== can ==view== or modify ==local== variables
* Storage used by local variables is ==released== when ==subroutine ends==
* local variable ==name== can have the ==same name== as a local variable in another function without creating a name clash
* Essential when writing ==recursive== procedures, as well as procedures executed by ==multiple== execution ==threads==

**Local Variables**

To explicitly create local variables, ==subtract== total ==size== from ESP.

```c
void MySub()
{
   int X=10;
   int Y=20;
}
```

```assembly
MySub PROC
	push	ebp
	mov	ebp,esp
	sub	esp,8			   ; create variables
	mov	DWORD PTR [ebp-4],10	   ; X
	mov	DWORD PTR [ebp-8],20	   ; Y
	; ... Do something
	mov	esp,ebp	  ; remove locals from stack
	pop	ebp
	ret
MySub ENDP				LocalVars.asm
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325085750014.png" alt="image-20220325085750014" style="zoom:67%;" />

### ENTER and LEAVE

* ENTER instruction creates stack frame for a called procedure
  * pushes EBP on the stack (push ebp)
  * sets EBP to the base of the stack frame (mov ebp, esp)
  * reserves space for local variables (sub esp, n)
  * Syntax: ENTER numBytesReserved, nestingLevel (=0)
* LEAVE instruction terminates the stack frame for a called procedure
  * restores ESP to release local variables (mov esp, ebp)
  * pops EBP for the caller (pop ebp)

### LEAVE Instruction

Terminates the stack frame for a procedure.

```assembly
MySub PROC
	enter 8,0
	...
	...
	...
	leave
	ret
MySub ENDP
```

Equivalent operations

```assembly
; enter 8,0
push	ebp
mov	ebp,esp
sub	esp,8      ; 2 local DWORDs
```

```assembly
; leave
mov	esp,ebp  ; free local space
pop	ebp
```

### LOCAL Directive

* The LOCAL directive declares a list of local variables

  * immediately follows the PROC directive
  * each variable is assigned a type

* Syntax:

  * ```assembly
    LOCAL varlist
    ```

* Example:

  ```assembly
  MySub PROC
  	LOCAL var1:BYTE, var2:WORD, var3:SDWORD
  ```

### Using LOCAL

Examples:

```assembly
LOCAL flagVals[20]:BYTE	; array of bytes

LOCAL pArray:PTR WORD	; pointer to an array

myProc PROC,			; procedure
	LOCAL t1:BYTE,		; local variables
```

#### LOCAL Example

```assembly
BubbleSort PROC
	LOCAL temp:DWORD, 
         SwapFlag:BYTE
	. . .
	ret
BubbleSort ENDP
```

MASM generates:

```assembly
BubbleSort PROC
	push ebp              	; enter 8, 0
	mov  ebp,esp
	add  esp,0FFFFFFF8h   	; add -8 to ESP
	. . .
	mov  esp,ebp          	; leave
	pop  ebp
	ret
BubbleSort ENDP				;See LocalExample.asm
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325090155527.png" alt="image-20220325090155527" style="zoom:67%;" />

### LEA Instruction

* LEA returns offsets of direct and indirect operands

  * OFFSET operator only returns constant offsets

* LEA required when obtaining offsets of stack parameters & local variables

* Example

  ```assembly
  CopyString PROC,
  	count:DWORD
  	LOCAL temp[20]:BYTE
  
  	mov edi,OFFSET count	; invalid operand
  	mov esi,OFFSET temp		; invalid operand
  	lea edi,count			; ok
  	lea esi,temp			; ok
  ```

* An example of C++ equivalent assembly code, see text

#### LEA Example

* Suppose you have a Local variable at [ebp-8]

* And you need the address of that local variable in ESI

* You cannot use this:

  * ```assembly
    mov esi, OFFSET [ebp-8]   	; error
    ```

* Use this instead:	

  * ```assembly
    lea esi,[ebp-8]
    ```

### WriteStackFrame Procedure

* Displays contents of current stack frame

  * Prototype:

    * ```assembly
      WriteStackFrame PROTO,
      numParam:DWORD,     ; number of passed parameters
      numLocalVal: DWORD, ; number of DWordLocal variables
      numSavedReg: DWORD  ; number of saved registers
      ```

### All in Stack Frame

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325090536475.png" alt="image-20220325090536475" style="zoom:67%;" />

## Recursion

* What is Recursion?
* Recursively Calculating a Sum
* Calculating a Factorial

### What is Recursion?

* The process created when . . .

  * A ==procedure== calls ==itself==
  * ==Procedure== A calls ==procedure== B, which in turn calls ==procedure== A

* Using a graph in which each node is a procedure and each edge is a ==procedure call==, recursion forms a cycle:

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325090713719.png" alt="image-20220325090713719" style="zoom:67%;" />

### Recursively Calculating a Sum

The CalcSum procedure recursively calculates the sum of an array of integers. Receives: ECX = count. Returns: EAX = sum

```assembly
CalcSum PROC
	cmp ecx,0		; check counter value
    jz L2			; quit if zero
    add eax,ecx		; otherwise, add to sum
    dec ecx			; decrement counter
    call CalcSum	; recursive call
L2: ret
CalcSum ENDP
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325090751663.png" alt="image-20220325090751663" style="zoom:67%;" />

### Calculating a Factorial

This function calculates the factorial of integer n. A new value of n is saved in each stack frame:

```c
int factorial(int n)
{
	if(n == 0)
	  return 1;
	else
	  return n * factorial(n-1);
}
```

> As each call instance returns, the product it returns is multiplied by the previous value of n.

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325090819132.png" alt="image-20220325090819132" style="zoom:67%;" />

```assembly
Factorial PROC
	push ebp
	mov  ebp,esp
	mov  eax,[ebp+8]		; get n
	cmp  eax,0				; n > 0?
	ja   L1					; yes: continue
	mov  eax,1				; no: return 1
	jmp  L2

L1:	dec  eax
	push eax				; Factorial(n-1)
	call Factorial

; Instructions from this point on excursion when each recursive call returns.

ReturnFact:
	mov  ebx,[ebp+8]   		; get n
	mul  ebx          		; eax = eax * ebx

L2:	pop  ebp				; return EAX
	ret  4					; clean up stack
Factorial ENDP
```

> Suppose we want to calculate 12!
>
> <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325090927218.png" alt="image-20220325090927218" style="zoom:67%;" />
>
> This diagram shows the first few stack frames created by recursive calls to Factorial
> Each recursive call uses 12 bytes of stack space.

> <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325091027018.png" alt="image-20220325091027018" style="zoom:67%;" />
>
> ```pseudocode
> => F: push ebp0, eax is 3
>      L1, eax=2, push 2
>      => F: push ebp1, eax is 2
>            L1, eax=1, push 1
>            => F: push ebp2, eax is 1
>                  L1, eax=0, push 0
>                  => F: push ebp3, eax is 0
>                       eax=1
>                       L2, pop ebp3
>                  <=
>                  [ebp3+8] is 1, 1*1
>                  L2, pop ebp2
>            <=
>            [ebp2+8] is 2, 1*2
>            L2, pop ebp1
>      <=
>      [ebp1+8] is 3, 2*3
>      L2, pop ebp0
> <=
> eax is 6
> RetuenMain
> 
> ```

## INVOKE, ADDR, PROC, and PROTO

* INVOKE Directive
* ADDR Operator
* PROC Directive
* PROTO Directive
* Parameter Classifications
* Example: Exchanging Two Integers
* Debugging Tips

### INVOKE Directive

* In 32-bit mode, the INVOKE directive is a powerful replacement for Intel’s CALL instruction that lets you pass multiple arguments 

* Syntax:

  * ```assembly
    INVOKE procedureName [, argumentList]
    ```

* ArgumentList is an optional comma-delimited list of procedure arguments
  Arguments can be:

  * immediate values and integer expressions
  * variable names
  * address and ADDR expressions
  * register names
  

  > Not in 64-bit mode!

#### INVOKE Examples

```assembly
.data
byteVal BYTE 10
wordVal WORD 1000h
.code
	; direct operands:
	INVOKE Sub1,byteVal,wordVal

	; address of variable:
	INVOKE Sub2,ADDR byteVal

	; register name, integer expression:
	INVOKE Sub3,eax,(10 * 20)

	; address expression (indirect operand):
	INVOKE Sub4,[ebx]
```

### ADDR Operator

* Returns a near or far pointer to a variable, depending on which memory model your program uses:

  * Small model: returns 16-bit offset
  * Large model: returns 32-bit segment/offset
  * Flat model: returns 32-bit offset

* Simple example:

  ```assembly
  .data
  myWord WORD ?
  .code
  INVOKE mySub,ADDR myWord
  ```

  > Not in 64-bit mode!

### PROC Directive

* The PROC directive declares a procedure

  * Syntax:
  * label PROC [attributes] [USES regList], paramList

* The USES clause must be on the same line as PROC.

* Attributes: distance, language type, visibility

* ParamList is a list of parameters separated by commas.

  * ```assembly
    label PROC, parameter1, parameter2, …, parameterN
    ```

    * Each parameter has the following syntax:

  * ```assembly
    paramName : type
    ```

* type must either be one of the standard ASM types  (BYTE, SBYTE, WORD, etc.), or it can be a pointer to one of these types. 

* Alternate format permits parameter list to be on one or more separate lines:

  ```assembly
  label PROC,
  	paramList
  ```

* The ==parameters== can be on the same line . . .

  * ```assembly
    param-1:type-1, param-2:type-2, . . ., param-n:type-n
    ```

* Or they can be on separate lines:

  * ```assembly
    param-1:type-1, 
    param-2:type-2,
    . . ., 
    param-n:type-n
    ```

#### Example: AddTwo Procedure

* AddTwo receives two integers and returns their sum in EAX.
* See Params.asm

```assembly
AddTwo PROC,
	val1:DWORD, val2:DWORD

	mov eax,val1
	add eax,val2
	ret
AddTwo ENDP
___________________________

myData WORD 1000h
invoke AddTwo, 1, myData
```

MASM Generates:

```assembly

 AddTwo PROC,
	val1:DWORD, val2:DWORD
	push   ebp
 	mov    ebp, esp
 	mov    eax,val1
 	add    eax,val2
	leave  
 	ret    00008h
 AddTwo ENDP
 ___________________________

  sub    esp, 002h
  push   myData
  push   +000000001h
  call   AddTwo
```

#### Example: FillArray

FillArray receives a ==pointer== to an array of bytes, a ==single== byte fill value that will be ==copied== to each element of the array, and the size of the array.

```assembly
FillArray PROC,
	pArray:PTR BYTE, fillVal:BYTE
	arraySize:DWORD

	mov ecx,arraySize
	mov esi,pArray
	mov al,fillVal
L1:	mov [esi],al
	inc esi
	loop L1
	ret
FillArray ENDP
```

### PROTO Directive

* Creates a procedure ==prototype==

* Syntax:

  * ```assembly
    label  PROTO  paramList
    ```

* Parameter list **not** permitted in **64-bit** mode
* Every procedure called by the **INVOKE** directive must have a **prototype**

**PROTO Directive**

* Standard configuration: PROTO appears at **top** of the program listing, INVOKE appears in the code segment, and the procedure implementation occurs later in the program:

```assembly
MySub PROTO  	; procedure prototype

.code
INVOKE MySub 	; procedure call


MySub PROC 	; procedure implementation
	.
	.
MySub ENDP
```

#### PROTO Example

> Prototype for the ArraySum procedure, showing its parameter list:

```assembly
ArraySum PROC USES esi ecx,
	ptrArray:PTR DWORD,	; points to the array
	szArray:DWORD	; array size	
	...
ArraySum ENDP


ArraySum PROTO,
	ptrArray:PTR DWORD,	; points to the array
	szArray:DWORD	; array size
```

> Parameters are not permitted in 64-bit mode.

### Assembly Time Argument Checking

```assembly
mySub1 PROTO, p1:BYTE, p2:WORD, p3:PTR BYTE 
invoke mySub1, byte_1, byte_1, ADDR byte_1
```

MASM Generates the following and no error detected:

```output
0000001A  68 00000000 R   *	 push   OFFSET byte_1
0000001F  A0 00000000 R   *	 mov    al, byte_1
00000024  0F B6 C0	  	  *	 movzx  eax, al
00000027  50		  	  *	 push   eax
00000028  A0 00000000 R   *	 mov    al, byte_1
0000002D  50		  	  *	 push   eax
0000002E  E8 00000022	  *	 call   mySub1
```

> Explain why use movzx and push eax?
>
> because parameters are not only 16-bit

### Parameter Classifications

* An input parameter is data passed by a calling program to a procedure. 
  * The called procedure is not expected to modify the corresponding parameter variable, and even if it does, the modification is confined to the procedure itself.
* An output parameter is created by passing a pointer to a variable when a procedure is called. 
  * The procedure does not use any existing data from the variable, but it fills in a new value before it returns.
* An input-output parameter is a pointer to a variable containing input that will be both used and modified by the procedure. 
  * The variable passed by the calling program is modified.

#### Example: Exchanging Two Integers

The ==Swap== procedure exchanges the values of two 32-bit integers. pValX and pValY do not change values, but the integers they point to are modified.

```assembly
Swap PROC USES eax esi edi,
    pValX:PTR DWORD,	; pointer to first integer
    pValY:PTR DWORD		; pointer to second integer

    mov esi,pValX		; get pointers
    mov edi,pValY
    mov eax,[esi]		; get first integer
    xchg eax,[edi]		; exchange with second
    mov [esi],eax		; replace first integer
    ret
Swap ENDP
```

### Multimodule Programs

* A **multimodule program** is a ==program== whose source code has been ==divided up== into ==separate== ASM files.
* Each ASM file (module) is assembled into a separate OBJ file.
* All OBJ files belonging to the same program are linked using the link utility into a single EXE file.
  * This process is called static linking

#### Advantages

* Large programs are easier to write, maintain, and debug when divided into separate source code modules.
* When changing a line of code, only its enclosing module needs to be assembled again. Linking assembled modules requires little time.
* A module can be a container for logically related code and data (think object-oriented here...)
  * ==encapsulation==: procedures and variables are automatically hidden in a module unless you declare them public

#### Creating a Multimodule Program

* Here are some basic steps to follow when creating a multimodule program:
  * Create the ==main== module
  * Create a ==separate== source code module for each ==procedure== or ==set== of related procedures
  * Create an ==include== file that contains procedure ==prototypes== for external procedures (ones that are called between modules)
  * Use the ==INCLUDE== directive to make your ==procedure== prototypes available to ==each== module

#### Example: ArraySum Program

> Let's review the ArraySum program from Chapter 5. 

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325092435845.png" alt="image-20220325092435845" style="zoom:67%;" />

> Each of the four white rectangles will ==become== a module. This will be a 32-bit application.

Sample Program output

```output
Enter a signed integer: -25

Enter a signed integer: 36

Enter a signed integer: 42

The sum of the integers is: +53
```

### INCLUDE File

```assembly
INCLUDE Irvine32.inc

PromptForIntegers PROTO,
	ptrPrompt:PTR BYTE,		; prompt string
	ptrArray:PTR DWORD,		; points to the array
	arraySize:DWORD			; size of the array

ArraySum PROTO,
	ptrArray:PTR DWORD,		; points to the array
	count:DWORD				; size of the array

DisplaySum PROTO,
	ptrPrompt:PTR BYTE,		; prompt string
	theSum:DWORD			; sum of the array
```

### Saving and Restoring Registers

* Push registers on stack just after assigning ESP to EBP
  * local registers are modified inside the procedure

```assembly
MySub_ PROC
	push	ebp
	mov		ebp,esp
	push	ecx	
	push	edx
	mov		eax,[ebp+8]	
	; Do something...
	pop		edx
	pop		ecx
	pop		ebp
	ret		4		
MySub_ ENDP
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325092614930.png" alt="image-20220325092614930" style="zoom:67%;" />

### Stack Affected by USES Operator

```assembly
MySub1 PROC USES ecx edx
    push	ebp
    mov		ebp,esp
    mov		eax,[ebp+8]
	; ...
    ret
MySub1 ENDP
```

USES operator generates:

```assembly
MySub1 PROC
  push	ecx
  push	edx

  push	ebp
  mov	ebp,esp
  mov	eax,[ebp+8]
  ; ...
  pop	edx
  pop	ecx
ret
```

> Where is ebp+8 pointing to? ==ECX==

### Passing 8-bit and 16-bit Arguments

* Cannot push 8-bit values on stack

* Pushing 16-bit operand may cause page fault or ESP alignment problem

  * incompatible with Windows API functions

* ==Expand== smaller arguments into 32-bit values, using ==MOVZX== or ==MOVSX==:

  ```assembly
  .data
  charVal BYTE 'x'	
  .code
  	movzx	eax,charVal
  	push	eax
  	call	Uppercase
  ```

### Passing 64-bit Arguments

* Push high-order values on the stack first; work backward in memory

* Results in little-endian ordering of data

* Example:

  ```assembly
  .data
  longVal QWORD 1234567800ABCDEFh
  .code
  	push	DWORD PTR longVal + 4	; high doubleword
  									; 12345678
  	push	DWORD PTR longVal		; low doubleword
  	call	WriteHex64
  ```

  > What’s stack memory look like?
  >
  > ```output
  > ef cd ab 00 78 56 34 12
  > ```

### Non-Doubleword Local Variables

* Local variables can be ==different== sizes
* How created in the stack by LOCAL directive:
  * 8-bit: assigned to next available byte
  * 16-bit: assigned to next even (word) boundary
  * 32-bit: assigned to next doubleword boundary

### Local Byte Variable

```assembly
Example1 PROC
   LOCAL var1:BYTE
   mov al,var1            ; [EBP - 1]
   ret
Example1 ENDP
```

* As stack offsets default to 32 bits, decrement ESP by 4

* Place var1 at [EBP-1] and leave three bytes below it unused (nu)

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325093045336.png" alt="image-20220325093045336" style="zoom:67%;" />

### The Microsoft x64 Calling Convention

* CALL subtracts 8 from RSP
* First four parameters are placed in RCX, RDX, R8, and R9. Additional parameters are pushed on the stack.
* Parameters less than 64 bits long are not zero extended
* Return value in RAX if <= 64 bits

### Java Bytecodes

* Stack-oriented instruction format
  * operands are on the stack
  * instructions pop the operands, process, and push result back on stack
* Each operation is atomic
* Might be translated into native code by a just in time compiler

### Java Virtual Machine (JVM)

* Essential part of the Java Platform
* Executes compiled ==bytecodes==
  * machine language of compiled Java programs

### Java Methods

* Each method has its ==own== stack frame
* ==Areas== of the stack frame:
  * local variables
  * operands
  * execution environment

### Bytecode Instruction Format

* ==1-byte== opcode
  * iload, istore, imul, goto, etc.
  * ==zero== or more operands
* ==Disassembling== Bytecodes
  * use javap.exe, in the Java Development Kit (JDK)

### Primitive Data Types

> Signed integers are in twos complement format, stored in big-endian order

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325093309917.png" alt="image-20220325093309917" style="zoom:67%;" />

### JVM Instruction Set

* Comparison Instructions pop two operands off the stack, compare them, and push the result of the comparison back on the stack

* Examples: ==fcmp== and ==dcmp==

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325093337549.png" alt="image-20220325093337549" style="zoom:67%;" />

* Conditional Branching 

  * jump to label if st(0) <= 0
    * ==ifle== label

* Unconditional Branching

  * call subroutine
    * ==jsr== label

### Java Disassembly Examples

Adding Two Integers

```java
int A = 3;
int B = 2;
int sum = 0;
sum = A + B;
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325093432182.png" alt="image-20220325093432182" style="zoom:67%;" />

Adding Two Doubles

```java
double A = 3.1;
double B = 2;
double sum = A + B;
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325093504057.png" alt="image-20220325093504057" style="zoom:67%;" />

Conditional Branch

```java
double A = 3.0;
boolean result = false;
if( A > 2.0 )
   result = false;
else
   result = true;
```

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325093557239.png" alt="image-20220325093557239" style="zoom:67%;" />
<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220325093606200.png" alt="image-20220325093606200" style="zoom:67%;" />

### .NET Assembly in CLR

* The .NET Framework provides a run-time environment called the common language runtime, which runs the code and provides .NET services.
* Assemblies are the building blocks of .NET Framework applications. 
* You can use the [Ildasm.exe (MSIL Disassembler)](https://msdn.microsoft.com/en-us/library/f7dy01k1%28v=vs.110%29.aspx) to view Microsoft intermediate language (MSIL) information in a file. 

## Summary

* Stack parameters
  * more convenient than register parameters
  * passed by value or reference
  * ENTER and LEAVE instructions
* Local variables
  * created on the stack below stack pointer
  * LOCAL directive
* Recursive procedure calls itself
* Calling conventions (C, stdcall)
* MASM procedure-related directives
  * INVOKE, PROC, PROTO
* Java Bytecodes – another approach to programming

# Disk Fundamentals

* Disk Storage Systems
* File Systems
* Disk Directory
* Reading and Writing Disk Sectors (7305h)
* System-Level File Functions

## Disk Storage Systems

* Tracks, Cylinders, and Sectors
* Disk Partitions (Volumes)

### Tracks and Sectors

* Physical disk geometry - a way of describing the disk’s structure to make it readable by the system BIOS
* Track - concentric circle containing data
* Sector - part of a track

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401084139867.png" alt="image-20220401084139867" style="zoom:67%;" />

### Cylinders and Seeking

* Cylinder - all tracks readable from one head position
* Seek - move read/write heads between tracks

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401084119100.png" alt="image-20220401084119100" style="zoom:67%;" />

## Disk Formatting

* Physical formatting
  * low-level formatting
  * Usually done at the factory. 
  * Must be done before logical formatting
  * Defines the tracks, sectors, and cylinders
* Logical formatting
  * Permits disk to be accessed using sequentially numbered logical sectors
  * Installs a file system (ex: NTFS)
  * May install an operating system

## Fragmentation

* A fragmented file is one whose sectors are no longer located in contiguous areas of the disk.
  * cause read/write heads to skip
  * slower file access
  * possible read/write errors

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401084316119.png" alt="image-20220401084316119" style="zoom:67%;" />

## Translation

* Translation - conversion of physical disk geometry to a sequence of logical sector numbers
* Performed by a hard disk controller (filmware)
* Logical sector numbers are numbered

## Disk Partitions

* Logical units that divide a physical hard disk
  * Also called volumes
* Primary partition
  * Up to four permitted
  * Each may boot a different OS
* Extended partition
  * Maximum of one permitted
  * May be divided into multiple logical partitions, each with a different drive letter
* Primary and Extended
  * Up to three primary and one extended

## Logical Partitions

* Created from an extended partition
* No limit on the number
* Each has a separate drive letter
* Usually contain data
* Can be bootable (ex: Linux)

## Disk Partition Table

* Located in the disk's Master Boot Record (MBR), following a block of executable code
* Four entries, one for each possible partition
* Each entry contains the following fields:
  * state (non-active, bootable)
  * type of partition (BigDOS, Extended, . . .)
  * beginning head, cylinder, & sector numbers
  * ending head, cylinder, & sector numbers
  * offset of partition from MBR
  * number of sectors in the partition

### Cascading Partition Tables

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401084650087.png" alt="image-20220401084650087" style="zoom:67%;" />

Boot = bootable (system)
NA = non active
BigDOS = over 32 MB

#### Dual-Boot Example

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401084712235.png" alt="image-20220401084712235" style="zoom:67%;" />

* System 98 and Win2000-A are bootable partitions
  * One is called the system partition when active
* DATA_1 and BACKUP are logical partitions
  * Their data can be shared by both operating systems

## Master Boot Record (MBR)

* The MBR contains the following elements:
  * Disk partititon table
  * A program that jumps to the boot sector of the system partition

## File Systems

* Directory, File, Cluster Relationships
* Clusters
* FAT12
* FAT16
* FAT32
* NTFS
* Primary Disk Areas

### File System

* This is what it does for you:
  * Keeps track of allocated and free space
  * Maintains directories and filenames
  * Tracks the sector location of each file and directory

### Directory, File, Cluster, Sector Relationships

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401084856832.png" alt="image-20220401084856832" style="zoom:67%;" />

### Cluster

* Smallest unit of space used by a file
* Consists of one or more adjacent sectors
* Size depends on both the type of file system in use and the disk partition size
* A file is a linked sequence of clusters. Example:

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401084936711.png" alt="image-20220401084936711" style="zoom:67%;" />

* A file always uses at least one cluster
* A high percentage of space may be wasted
* Example: 8,200-byte file requires three 4K clusters:

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401085006119.png" alt="image-20220401085006119" style="zoom:67%;" />

### FAT12

* Designed for diskettes
* Each FAT entry is 12 bits
* Very little fault tolerance
  * two copies of the FAT (cluster table)
* Optimal storage for small files
  * 512-byte clusters

### FAT16

* MS-DOS format for hard disks
* 16-bit FAT entries
* Large cluster size when disk > 1 GB
  * inneficient for small files
* Max 2 GB size under MS-DOS
* Little or no recovery from read/write errors

### FAT32

Supports long filenames
Supported by all version of MS-Windows from Windows 95 onward
(except Windows NT)
32-bit FAT entries
32 GB maximum volume size
Improved recovery from read/write errors

### NTFS

* Supported by Windows NT, 2000, and XP
* Handles large volumes
* can span multiple hard drives
* Efficient cluster size (4K) on large volumes
* Unicode filenames
* Permissions on files & folders
* Share folders across network
* Built-in compression and encryption
* Track changes in a change journal
* Disk quotas for individuals or groups
* Robust error recovery
* Disk mirroring

### Boot Record

* Fields in a typical MS-DOS boot record:
  * Jump to boot code (JMP instruction)
  * Manufacturer name, version number 
  * Bytes per sector
  * Sectors per cluster
  * Number of reserved sectors (preceding FAT #1)
  * Number of copies of FAT
  * Maximum number of root directory entries
  * Number of disk sectors for drives under 32 MB
  * Media descriptor byte
  * Size of FAT, in sectors
  * Sectors per track
  * Number of drive heads
  * Number of hidden sectors
  * Number of disk sectors for drives over 32 MB
  * Drive number (modified by MS-DOS)
  * Reserved
  * Extended boot signature (always 29h)
  * Volume ID number (binary)
  * Volume label
  * File-system type (ASCII)
  * Start of boot program and data

## Keeping Track of Files

* MS-DOS Directory Structure
* Long Filenames in MS-Windows
* File Allocation Table

### MS-DOS Directory Structure

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401085432609.png" alt="image-20220401085432609" style="zoom:67%;" />

Time field equals 4DBDh (9:45:58), and the Date field equals 247Ah (March 26, 1998). Attribute is normal:

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401085502217.png" alt="image-20220401085502217" style="zoom:67%;" />

### Date and Time Fields

* Date stamp field:
  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401085546128.png" alt="image-20220401085546128" style="zoom:67%;" />

* Time stamp field:

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401085606820.png" alt="image-20220401085606820" style="zoom:67%;" />

### File Attribute Values

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401085628414.png" alt="image-20220401085628414" style="zoom:67%;" />

> What type of file has attribute 00100111 . . . ?

### Long Filenames in Windows

> Filename: ABCDEFGHIJKLMNOPQRSTUV.TXT 

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401085657797.png" alt="image-20220401085657797" style="zoom:67%;" />

### File Allocation Table

* A map of all clusters on the disk, showing their ownership by specific files

* Each entry corresponds to a cluster number

* Each cluster contains one or more sectors

* Each file is represented in the FAT as a linked list, called a cluster chain.

* Three types of FAT's, named after the length of each FAT entry:

  * FAT-12
  * FAT-16
  * FAT-32

* Each entry contains an n-bit integer that identifies the next entry. (n=12,16, or 32)

* Two cluster chains are shown in the following diagram, one for File1, and another for File2:

  <img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401085745992.png" alt="image-20220401085745992" style="zoom:67%;" />

## Reading and Writing Disk Sectors (7305h)

* INT 21h, Function 7305h (absolute disk read and write) 
* Reads and writes logical disk sectors
* Runs only in 16-bit Real-address mode 
* Does not work under Windows 2000, XP, Vista, Windows 7
  * Tight security!

### DISKIO Structure

> Used by Function 7305h:
>
> ```assembly
> DISKIO STRUCT
> 	startSector DWORD 0		; starting sector number
> 	numSectors  WORD 1		; number of sectors
> 	bufferOfs   WORD buffer	; buffer offset
> 	bufferSeg   WORD @DATA	; buffer segment
> DISKIO ENDS
> ```

#### Example

> Example: Read one or more sectors from drive C:
>
> ```assembly
> .data
> buffer BYTE 512 DUP(?)
> diskStruct DISKIO <>
> .code
> 	mov ax,7305h		; absolute Read/Write
> 	mov cx,0FFFFh 		; always this value
> 	mov dl,3			; drive C
> 	mov bx,OFFSET diskStruct	
> 	mov si,0			; read sector
> 	int 21h
> ```

### Sector Display Program

Pseudocode:

```pseudocode
Ask for starting sector number and drive number
do while (keystroke <> ESC)
	Display heading
	Read one sector
	If MS-DOS error then exit
	Display one sector
	Wait for keystroke
	Increment sector number
end do
```

## System-Level File Functions

* Common Disk-Related Functions
* Get Disk Free Space
* Create Subdirectory
* Remove Subdirecrory
* Set Current Directory
* Get Current Directory

### Common Disk-Related Functions

<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401090204633.png" alt="image-20220401090204633" style="zoom:67%;" />
<img src="C:\Users\weikang\AppData\Roaming\Typora\typora-user-images\image-20220401090211194.png" alt="image-20220401090211194" style="zoom:67%;" />

### ExtGetDskFreSpcStruc Structure

> Structure data returned by Function 7303h

* StructSize: A return value that represents the size of the ExtGetDskFreSpcStruc structure, in bytes.
* Level: Always 0.
* SectorsPerCluster: The number of sectors inside each cluster. 
* BytesPerSector: The number of bytes in each sector. 
* AvailableClusters: The number of available clusters. 
* TotalClusters: The total number of clusters in the volume.
* AvailablePhysSectors: The number of physical sectors available in the volume, without adjustment for compression. 
* TotalPhysSectors: The total number of physical sectors in the volume, without adjustment for compression. 
* AvailableAllocationUnits: The number of available allocation units in the volume, without adjustment for compression. 
* TotalAllocationUnits: The total number of allocation units in the volume, without adjustment for compression. 
* Rsvd: Reserved member. 

### Function 7303h – Get Disk Free Space

* AX = 7303h
* ES:DI points to a ExtGetDskFreSpcStruc
* CX = size of the ExtGetDskFreSpcStruc variable
* DS:DX points to a null-terminated string containing the drive name

### Create Subdirectory

```assembly
.data
pathname BYTE "\ASM",0

.code
	mov ah,39h				; create subdirectory
	mov dx,OFFSET pathname
	int 21h
	jc  DisplayError
	.
	.
DisplayError:
```

### Remove Subdirecrory

```assembly
.data
pathname  BYTE  "C:\ASM",0

.code	
	mov ah,3Ah            	; remove subdirectory
	mov dx,OFFSET pathname
	int 21h
	jc  DisplayError
	.
	.
DisplayError:
```

### Set Current Directory

```assembly
.data
pathname  BYTE "C:\ASM\PROGS",0

.code
	mov ah,3Bh				; set current directory
	mov dx,OFFSET pathname
	int 21h
	jc  DisplayError
	.
	.
DisplayError:
```

### Get Current Directory

```assembly
.data
pathname  BYTE 64 dup(0)  	; path stored here by MS-DOS

.code
	mov ah,47h				; get current directory path
	mov dl,0				; on default drive
	mov si,OFFSET pathname     
	int 21h
	jc  DisplayError
	.
	.
DisplayError:
```

## Summary

* Disk controller: acts as a broker between the hardware and the operating system
* Disk characteristics
  * composed of tracks, cylinders, sectors
  * average seek time, data transfer rate
* Formatting & logical characteristics
  * master boot record, contains disk partition table
  * clusters – logical storage units
  * file allocation table – used by some systems
  * directory – root directory, subdirectories.
