# [Enhance RISC-V Architecture Support in RTOS Embox](https://summer-ospp.ac.cn/org/prodetail/249c00148?list=org&navpage=org)

## Project Overview
This project aims to enhance the RISC-V architecture support in the Embox RTOS by integrating key components such as:
- **Core Local Interruptor (CLINT)**
- **Platform-Level Interrupt Controller (PLIC)**
- **Floating-Point Unit (FPU)**
- **Physical Memory Protection (PMP)**

These additions will enable Embox to efficiently handle hardware interrupts, perform floating-point operations, and enforce memory protection. The integration of CLINT and PLIC will improve real-time interrupt handling, FPU support will enhance computational performance, and PMP will bolster security and stability by preventing unauthorized memory access.

## Key Features
- **CLINT and PLIC Integration**: Improves real-time handling of interrupts and timer management.
- **FPU Support**: Enhances computational capabilities for floating-point operations.
- **PMP Support**: Provides memory protection and access control to improve system security and stability.

## Merged Pull Requests
- [**Implement SiFive PLIC Support in Embox RTOS**](https://github.com/embox/embox/pull/3314)
  - Introduces the Platform-Level Interrupt Controller (PLIC) driver for the SiFive U54-MC Core. Includes functionality for enabling, disabling, setting priority, and handling interrupts for multiple harts (hardware threads).

- [**Implement RISC-V CLINT Support for Interrupt Control and Timer Management**](https://github.com/embox/embox/pull/3348)
  - Provides support for Core Local Interruptor (CLINT) functionality, crucial for managing interrupts and timers in RISC-V multi-hart configurations.

- [**Add SiFive CLINT Support for Multi-Hart Architecture**](https://github.com/embox/embox/pull/3356)
  - Extends CLINT support to handle multi-hart systems, improving efficiency in managing multiple hardware threads.

## Summary
- **Project Website**: [OSPP 2024](https://summer-ospp.ac.cn/org/prodetail/249c00148?list=org&navpage=org)
- **Upstream Repository Fork**: [SurajSonawane2415/embox](https://github.com/SurajSonawane2415/embox)
- **Project Proposal**: [View Proposal](https://docs.google.com/document/d/1aRfXzFN_mCHorJmdMGZrrZTLVfves6QpZ8A1rbIRiHk/edit?usp=sharing)

## Project Objectives
- [x] [Add SiFive PLIC support](https://github.com/embox/embox/pull/3314)
- [x] [Add RISC-V CLINT support](https://github.com/embox/embox/pull/3348)
- [x] [Add SiFive CLINT support](https://github.com/embox/embox/pull/3356)
- [ ] Add PMP (Physical Memory Protection) Support
- [ ] Add FPU (Floating-Point Unit) Support
- [ ] Add additional RISC-V architecture components support

## Output
- Testing results with QEMU:
![Screenshot from 2024-07-19 20-50-51](https://github.com/user-attachments/assets/8ffb41e7-802b-47a7-91ad-79a0d032f5c7)

## Project Description

### 1. Physical Memory Protection (PMP)
To enhance secure processing and manage faults, Physical Memory Protection (PMP) limits the physical memory addresses accessible by software running on a hart. PMP provides per-hart machine-mode control registers to specify access privileges (read, write, execute) for each memory region. This feature helps prevent unauthorized access and interference from third-party code, as well as detect stack overflows, thus improving system safety and security.

![Screenshot 2024-07-31 at 20-28-32 Antmicro · Adding Physical Memory Protection to the VeeR EL2 RISC-V Core](https://github.com/user-attachments/assets/da7e99c7-3572-4510-842c-50a1a3ec50d2)


### 2. Core Local Interruptor (CLINT)
The Core Local Interruptor (CLINT) manages software and timer interrupts within the RISC-V architecture. The implementation of CLINT in Embox RTOS involves configuring software and timer interrupts, setting timer values, enabling interrupts, and managing interrupt claims and completions. This integration enhances Embox's real-time application capabilities in embedded systems.

![CLINT Integration](https://github.com/user-attachments/assets/6bf0d144-5f2e-43b0-92d3-14a4449743ed)

### 3. Platform-Level Interrupt Controller (PLIC)
Support for the Platform-Level Interrupt Controller (PLIC) has been added for the RISC-V architecture [link]. This project aims to integrate PLIC support specifically for the SiFive U54-MC board in Embox [Issue link]. 

The PLIC manages interrupts for the SiFive U54-MC Core Complex according to RISC-V standards. It supports up to 511 external interrupt sources with 7 priority levels. The implementation involves configuring interrupt sources, setting priorities, enabling interrupts, and handling claims and completions. This addition enhances real-time capabilities in embedded systems.

![PLIC Memory Map](https://github.com/user-attachments/assets/ed3af3f9-c55d-42a0-a10e-3e28fa5e21ab)

The PLIC memory map for the SiFive U54-MC Core Complex includes:
- **Source Priority Registers**: From `0x0C00 0004` to `0x0C00 0804`, holding interrupt source priority levels.
- **Pending Array**: Starting at `0x0C00 1000`, containing information about pending interrupts.
- **M-mode Enables**: Starting from `0x0C00 2000`, managing M-mode interrupt enables for each hart.
- **S-mode Enables**: Similar to M-mode, controlling S-mode interrupt enables for each hart.
- **Priority Thresholds**: Set using registers starting from `0x0C20 0000`.
- **Claim/Complete Registers**: Located at `0x0C20 0004`, used for the interrupt claim process.

### 4. Floating-Point Unit (FPU)
The Floating-Point Unit (FPU) provides functional units for performing mathematical operations, comparisons, and other tasks on floating-point values. It ensures efficient execution of floating-point instructions and enhances the handling of complex arithmetic operations, which is critical for real-time applications in embedded systems.


## Contributors
- [Suraj Sonawane](https://github.com/SurajSonawane2415)

## Mentors
- Aleksey Zhmulin
- Anton Bondrarev


