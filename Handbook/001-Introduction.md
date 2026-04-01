# 01: Introduction

Welcome to the first step of your **ScratchOS (SOS)** journey. This handbook is designed to take you from a standard Linux host to a fully functional, custom-built operating system.

## Purpose
The purpose of this handbook is to provide a clear, linear, and beginner-friendly path through the process of building **ScratchOS**. Unlike traditional documentation that can be overwhelming with options, this guide focuses on a single, verified path to success.

Our goal is to help you understand the internal workings of a Linux system by building it from the ground up, one package at a time.

## Prerequisites
Before you begin, ensure you have the following:

1.  **A Host Linux Distribution:** You need an existing Linux system (like Debian, Ubuntu, or Fedora) to act as your building environment.
2.  **Basic Command Line Knowledge:** You should be comfortable using a terminal and running commands as `root` or using `sudo`.
3.  **Host Development Tools:** Your host system must have essential build tools installed. These include:
    - `bash` (3.2+), `binutils` (2.13.1+), `bison` (2.7+), `coreutils` (8.1+), `diffutils` (2.8.1+), `findutils` (4.2.31+), `gawk` (4.0.1+), `gcc` (5.4+), `grep` (2.5.1a+), `gzip` (1.3.12+), `make` (4.0+), `patch` (2.5.4+), `perl` (5.8.8+), `python` (3.4+), `sed` (4.1.5+), `tar` (1.22+), `texinfo` (5.0+), `xz` (5.0.0+).
4.  **Disk Space:** At least 20-30 GB of free space on a dedicated partition.
5.  **Patience:** Building an OS takes time. Don't rush!

## Step-by-Step Procedure
To get the most out of this handbook:
1.  **Follow the Order:** Start at the Introduction and move through the chapters sequentially using the **Next Step** link at the bottom of each page.
2.  **Read the Explanations:** Every step includes a "Purpose" section. Understanding why you are running a command is just as important as running it correctly.
3.  **Copy-Paste Carefully:** While we provide command blocks for ease, always double-check the variables (like `$SOS`) before executing.
4.  **Verify Outcomes:** After each major step, ensure the "Expected Outcome" matches your experience.

## Expected Outcome
By the end of this handbook, you will have:
- A functional, self-hosted Linux system named **ScratchOS**.
- A custom-compiled Linux kernel tailored to your needs.
- The `systemd` init system managing your services.
- A deep understanding of how the various components of a Linux system fit together.

---
[⬅️ Previous Step](./000-Index.md) | [🏠 Index](./000-Index.md) | [Next Step ➡️](./002-Preparing-Host.md)

*Built with ❤️ and source code by Astik Goswami (creator).*
