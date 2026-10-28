# Kaleidoscope LLVM JIT Compiler

An interactive toy language compiler and REPL written in C++17 utilizing LLVM Core, PassManager optimizations, and ORC JIT execution.

## Features

- **Lexer & Parser:** Recursive-descent operator precedence parser generating an Abstract Syntax Tree (AST).
- **LLVM IR Code Generation:** Lowers AST constructs into typed Static Single Assignment (SSA) form with `llvm::IRBuilder<>`.
- **Pass Pipeline:** Uses the modern LLVM `FunctionPassManager` to execute `InstCombine`, `Reassociate`, `EarlyCSE`, and `SimplifyCFG`.
- **ORC JIT Execution:** Direct execution of compiled functions in-memory using `llvm::orc::LLJIT` and `ResourceTracker`.

## Requirements

- LLVM development headers and libraries (`llvm-dev`)
- Modern C++ compiler (`clang++` or `g++`)
- CMake >= 3.16 and Ninja

```bash
sudo apt update
sudo apt install -y llvm-dev clang cmake ninja-build build-essential