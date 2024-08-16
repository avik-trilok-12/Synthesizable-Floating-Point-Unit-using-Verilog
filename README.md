

---

# Synthesizable Floating Point Unit in Verilog

This repository contains Verilog implementations of a synthesizable Floating Point Unit (FPU) that supports 32-bit single-precision operations in compliance with the IEEE-754 standard. The supported operations include:

- **Addition and Subtraction**: Single-precision floating-point addition and subtraction.
- **Multiplication**: Single-precision floating-point multiplication.
- **Division**: Single-precision floating-point division using Newton-Raphson iterations.
- **Square Root**: Single-precision floating-point square root calculation.

## Overview of Operations

### 1. FloatAdd.v

- **Purpose**: Handles both addition and subtraction of single-precision floating-point numbers.
- **Method**: 
  - For subtraction, the sign bit of the second operand is inverted.
  - The values are **truncated** instead of rounded for the final result.

### 2. FloatMul.v

- **Purpose**: Performs multiplication of single-precision floating-point numbers.
- **Method**:
  - The values are **truncated** instead of rounded for the final result.

### 3. FloatDiv.v

- **Purpose**: Computes division of single-precision floating-point numbers.
- **Method**: 
  - The division is performed using the **Newton-Raphson** method, which finds the reciprocal of the divisor and multiplies it with the dividend.
  - This implementation uses 8 instances of multiplication and 3 instances of addition to compute the result.
  - The values are **truncated** rather than rounded.

## Features
- **IEEE-754 Compliant**: All operations adhere to the IEEE-754 standard for single-precision floating-point numbers.
- **Optimized Division**: Efficient division using Newton-Raphson iterations.
- **Modular Design**: Each operation is encapsulated in its own Verilog module for flexibility and reuse.
- **Synthesis Ready**: The design is fully synthesizable and can be deployed on FPGAs or ASICs.

---
