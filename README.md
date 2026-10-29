
# C++ Memory Management Simulation

## 1. Project Overview

This project implements a basic memory management simulator in C++.
It demonstrates how a heap manager allocates, deallocates, and
reallocates memory blocks in a simulated heap.

The program uses a console-based menu that allows users to perform
memory operations and view the heap state after each operation.

## 2. Objectives

- Simulate dynamic memory allocation.
- Implement memory deallocation and reallocation.
- Demonstrate external fragmentation.
- Merge adjacent free blocks using coalescing.
- Detect invalid memory access and double-free attempts.
- Display memory usage and free space.

## 3. Features

### Memory Allocation
The program uses the First-Fit strategy to find the first free block
large enough to satisfy an allocation request.

### Memory Deallocation
Users can free allocated blocks by entering their block IDs.

### Memory Reallocation
Existing blocks can be resized. The program attempts to expand a
block into adjacent free space before allocating a replacement block.

### Fragmentation
External fragmentation occurs when free memory is split into separate
blocks, preventing a large allocation even when total free memory
is sufficient.

### Coalescing
Adjacent free blocks are merged to create larger free memory regions.

### Error Handling
The simulator checks for:
- Invalid allocation sizes.
- Invalid block IDs.
- Double-free attempts.
- Out-of-bounds memory access.
- Invalid menu input.

## 4. Memory Management Strategy

The First-Fit allocation algorithm searches the heap from the
beginning and selects the first suitable free block.

If the selected block is larger than requested, it is split into
an allocated block and a remaining free block.

When memory is released, adjacent free blocks are merged through
coalescing to reduce external fragmentation.

## 5. Project Structure

memory-manager-simulation/
├── memory_manager.cpp
└── README.md

## 6. Requirements

- A C++ compiler such as GCC or MinGW.
- C++11 or later.
- A terminal or command prompt.

## 7. Compilation and Execution

Compile using GCC:

g++ -std=c++11 -Wall -Wextra memory_manager.cpp -o memory_manager

Run on Linux or macOS:

./memory_manager

Run on Windows:

memory_manager.exe

## 8. How to Use

1. Run the compiled program.
2. Enter the total simulated heap size.
3. Select an option from the menu.
4. Allocate memory by entering a requested size.
5. Free memory by entering an allocated block ID.
6. Reallocate a block by entering its ID and new size.
7. Check memory access by providing a block ID and offset.
8. Display the heap to inspect memory blocks.
9. Select 0 to exit.

## 9. Limitations

This is an educational simulation. It does not allocate or release
actual operating-system memory.

The heap uses a vector of memory block records, so its behavior
illustrates allocation strategies rather than the internal workings
of a production memory allocator.

## 10. Conclusion

This project demonstrates fundamental memory management concepts
including First-Fit allocation, deallocation, reallocation,
fragmentation, coalescing, and error handling.

It provides a practical introduction to system-level programming
concepts using C++.
