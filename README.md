# Enhance RISC-V Architecture Support in RTOS Embox

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
- **Upstream Repository Fork**: [SurajSonawane2415/embox](https://github.com/SurajSonawane2415/embox)
- **Project Proposal**: [View Proposal](https://docs.google.com/document/d/1aRfXzFN_mCHorJmdMGZrrZTLVfves6QpZ8A1rbIRiHk/edit?usp=sharing)

## Project Objectives
- [x] Add SiFive PLIC support
- [x] Add RISC-V CLINT support
- [x] Add SiFive CLINT support
- [ ] Add PMP (Physical Memory Protection) Support
- [ ] Add FPU (Floating-Point Unit) Support
- [ ] Add additional RISC-V architecture components support

## Contributors
- [Suraj Sonawane](https://github.com/SurajSonawane2415)

## Mentors
- Aleksey Zhmulin
- Anton Bondrarev


