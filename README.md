# Communication Buffer Implementation in C++

## Overview

This C++ program implements a communication buffer data structure for facilitating communication between processes in a Linux environment. The communication buffer allows the storage of elements in a First-In-First-Out (FIFO) or Last-In-First-Out (LIFO) order. The primary focus is on utilizing semaphores as synchronization mechanisms to prevent issues such as reading from an empty buffer, writing to a full buffer, and interference between processes reading and writing.

## Problem Description

In a multi-process environment, communication buffers play a crucial role in enabling processes to exchange data. The challenge lies in coordinating access to these buffers to avoid race conditions, ensuring orderly reading and writing operations.

## Communication Buffer

A communication buffer is a structured data container capable of holding up to M elements of the same type. Processes can extract elements from the buffer in either FIFO or LIFO order, providing flexibility in data retrieval.

## Synchronization with Semaphores

### 1. Preventing Reading from an Empty Buffer

To address the issue of reading from an empty buffer, semaphores are employed. A semaphore is used to track the number of elements in the buffer, ensuring that processes attempting to read are blocked when the buffer is empty.

### 2. Avoiding Writing to a Full Buffer

To prevent writing to a full buffer, another semaphore is used to track the available space in the buffer. Processes attempting to write are blocked when the buffer is at its capacity, allowing for orderly writing operations.

### 3. Avoiding Interference

Semaphores also play a crucial role in avoiding interference between processes reading and writing. By using semaphores to control access to the critical sections of the code, only one process can access the buffer at a time. This ensures the integrity of the buffer and prevents data corruption.
