# ScratchOS

A simple, easy-to-use distro with minimal headache. :)

**ScratchOS (SOS)** is a project and accompanying handbook designed to take you from a standard Linux host to a fully functional, custom-built operating system.

## Purpose

The purpose of this project is to provide a clear, linear, and beginner-friendly path through the process of building **ScratchOS**. Unlike traditional documentation that can be overwhelming with options, this guide focuses on a single, verified path to success.

My goal is to help you understand the internal workings of a Linux system by building it from the ground up, one package at a time.

## Prerequisites

Before you begin the handbook, ensure you have the following:

1.  **A Host Linux Distribution:** You need an existing Linux system (like Debian, Ubuntu, or Fedora) to act as your building environment.
2.  **Basic Command Line Knowledge:** You should be comfortable using a terminal and running commands as `root` or using `sudo` (i.e.: ls, cd, cat etc, everything else is taken care for you ;) ).
3.  **Host Development Tools:** Your host system must have essential build tools installed (e.g., `bash`, `binutils`, `gcc`, `make`, etc.).
4.  **Disk Space:** At least 20-30 GB of free space on a dedicated partition.
5.  **Patience:** Building an OS takes time. Don't rush!

## The Handbook

The `Handbook/` directory contains a step-by-step guide to building ScratchOS.

To get the most out of it:
1.  **Follow the Order:** Start at `Handbook/000-Index.md` or `Handbook/001-Introduction.md` and move through the chapters sequentially.
2.  **Read the Explanations:** Every step includes a "Purpose" section. Understanding *why* you are running a command is just as important as running it correctly.
3.  **Copy-Paste Carefully:** While we provide command blocks for ease, always double-check the variables before executing.
4.  **Verify Outcomes:** After each major step, ensure the "Expected Outcome" matches your experience.

## Expected Outcome

By the end of the handbook, you will have:
- A functional, self-hosted Linux system named **ScratchOS**.
- A custom-compiled Linux kernel tailored to your needs.
- The `systemd` init system managing your services.
- A deep understanding of how the various components of a Linux system fit together.

## Link to the handbook : [[000-Index]]

## Credits

Built with ❤️ and source code by Astik Goswami (creator).
