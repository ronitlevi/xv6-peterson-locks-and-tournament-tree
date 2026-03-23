# xv6 Synchronization

A low-level systems programming project implementing synchronization mechanisms in xv6.

This project extends the xv6 operating system with synchronization primitives and was developed as part of an Operating Systems course (2025).

It focuses on concurrency, mutual exclusion, and practical systems programming.

## Overview

The project was implemented in two stages:

1. **Peterson Locks in xv6**  
   Added kernel-managed Peterson locks exposed through system calls, allowing two processes to coordinate access to a critical section.

2. **Tournament Tree Library**  
   Built a userspace synchronization library on top of Peterson locks to support mutual exclusion among multiple processes using a tournament tree structure.

This project demonstrates how a theoretical synchronization algorithm can be adapted into a practical system in xv6.

The implementation bridges theoretical synchronization algorithms with practical kernel-level system design.

## Features

### Peterson Lock System Calls
- `peterson_create()`
- `peterson_acquire(int lock_id, int role)`
- `peterson_release(int lock_id, int role)`
- `peterson_destroy(int lock_id)`

### Tournament Tree Synchronization
- Userspace library for synchronization among multiple processes
- Binary-tree structure built from Peterson locks
- Per-process role assignment at each level of the tree
- Lock acquisition from leaf to root
- Lock release in reverse order

## Technologies

- C
- xv6 (RISC-V)
- Kernel system calls
- Userspace synchronization library
- Atomic operations and memory barriers

## Key Concepts

- Mutual exclusion
- Process synchronization
- Peterson lock
- Tournament tree
- Concurrency
- Yield-based waiting
- Atomic operations
- Memory ordering

## How to Run

1. Clone the xv6 repository
2. Apply the project changes
3. Build and run xv6:
   ```bash
   make qemu
   ```
4. Run the tournament test program:
   ```bash
   tournament
   ```

## What I Learned

- How synchronization mechanisms are implemented inside an operating system
- How Peterson's algorithm can be adapted for real systems
- How to expose kernel functionality through system calls
- How to build higher-level synchronization abstractions in userspace
- How concurrency issues are affected by memory ordering and atomic operations

## Contribution

This project was developed collaboratively in a team of two.

Collaborated with Sapir Tzoraro.
