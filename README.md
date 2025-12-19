Flight-Controller-Core 🚁

A Bare-Metal STM32F4 Firmware for Mission-Critical Flight Stabilization

This repository houses the foundational core of a flight controller built entirely from scratch in Embedded C. Designed to meet defence and aerospace standards for reliability, this project bypasses vendor abstraction layers (HAL) to interact directly with the silicon.

The goal is to build a deterministic, fail-safe IMU driver and control loop that runs on the "bare metal" of the ARM Cortex-M4 processor.
Key Features

    Zero-Dependency Architecture: No HAL, no Standard Peripheral Libraries, and no OS (yet). All drivers are written using direct memory access to hardware registers.

    Custom Boot Process: Includes a handwritten startup.c with a manually defined Vector Table and Reset Handler, replacing standard vendor startup files.

Core Drivers:

    UART: Custom serial driver for real-time telemetry and debugging.

    GPIO & Interrupts: Register-level implementation of EXTI and NVIC for low-latency event handling.

Timing: SysTick-based timekeeping for precise, non-blocking delays.

    Simulation Ready: Fully configured Renode scripts (.resc) for hardware-in-the-loop simulation without physical boards.

Tech Stack

    Target: STM32F4 Discovery (ARM Cortex-M4F)

    Language: C (C99/C11)

    Build System: GNU Make & GCC-ARM-None-EABI

    Simulation: Renode
