# MLIR Dialect Prototype – Matrix Multiplication Optimization

This project is a personal prototype that builds a **custom MLIR dialect** to optimize matrix multiplication using **loop tiling**, **loop fusion**, and **target-aware lowering**. It is based on the LLVM/MLIR infrastructure and simulates performance enhancements for edge-style workloads.

---

## 🧠 Project Goal

To design and implement a **custom dialect in MLIR** that:
- Defines domain-specific operations like `matmul`
- Applies **transformation passes** for tiling and loop fusion
- Lowers to standard dialects (Affine → LLVM) for efficient codegen
- Demonstrates understanding of compiler IR design, MLIR extensibility, and edge-aware optimization

---

## 🏗️ Dialect Features

-  **Custom `matmul` Op**: Defined using TableGen and built with matrix-specific semantics
-  **Tile Size Attribute**: Used to partition matrices into blocks for better cache reuse
-  **Loop Fusion Pass**: Combines loops to reduce overhead and improve locality
-  **Lowering Pass**: Converts custom ops into Affine dialect → LLVM IR
-  **C++ Pass Infrastructure**: Built using MLIR pass manager and `PassRegistration`

---

## ⚙️ Technologies & Tools

- MLIR (Multi-Level Intermediate Representation)
- LLVM backend
- TableGen (for dialect definition)
- C++, CMake, Ninja

---

## 🔍 Repository Structure

```bash
.
├── include/mlir/Dialect/MyDialect/     # Custom dialect ops and TableGen definitions
├── lib/Dialect/MyDialect/              # Dialect registration and C++ implementation
├── lib/Transforms/                     # Tiling and fusion passes
├── test/                               # MLIR test files with custom ops and transformation flow
├── CMakeLists.txt                      # CMake build configuration
└── README.md                           # Project overview (this file)
