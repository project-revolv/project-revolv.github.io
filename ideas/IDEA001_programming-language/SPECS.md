# 📘 Delta Language Specification (Draft)

---

## 🧠 What is Delta?

**Delta** is a statically-typed, compiled, and self-hosting programming language designed to give developers the raw performance of C with the safety and ergonomics of modern languages — minus the bloat.

Delta is built to evolve itself. It’s simple where it should be, powerful where it must be, and modular by default. Whether you’re building kernels, compilers, or high-performance apps, Delta gets out of your way and lets you focus on the code.

---

## 🎯 Design Goals

- ⚡ **Fast to run**: LLVM-powered, no unnecessary abstraction
- 🎯 **Fast to write**: Clean syntax, no noise
- 🛠️ **Self-hosting**: The compiler is written in Delta
- 🧩 **Modular**: Minimal runtime, batteries optional
- 🔐 **Safe by default**: Memory safety without garbage collection
- 🧠 **Hackable**: Designed to evolve — including itself

---

## 🧱 Language Structure

### 🧵 Type System
- Static, strong typing
- Optional type inference
- First-class support for:
  - Primitives (int, float, bool, etc.)
  - Structs and enums
  - Generics
  - Reference (instead of pointer)
  - Functions
  - `match` construct's value

### 🧠 Syntax Style
Delta’s syntax is influenced by Go, Rust, and Swift:
- Curly-brace based (not whitespace-sensitive)
- Simple declaration syntax: `var`, `fn`, `type`
- No forced semicolons
- Allows inheritance, but composition-first
- Compile-time macros and basic metaprogramming planned

### 🔄 Compilation Flow

Delta’s architecture:
```
Source code (.dl)
  ↓
Lexer
  ↓
Parser
  ↓
 AST
  ↓
Intermediate Representation
  ↓
LLVM IR
  ↓
Machine Code
```

- Bootstrapping starts with external tools (ANTLR + host language)
- Later replaced with native compiler written in Delta

---

## 🧰 Toolchain

- `delta` CLI tool:
  - Build, test, format, and run code
- Built-in formatter and linter
- Docs generator from comments
- Local and global package manager (planned)

---

## 🗂️ Modules and Imports

- Explicit import paths (`import <std/io>`, `import "local_file.dl"`)
- Package-level visibility rules
- Namespace collision avoidance built-in

---

## ❌ Out of Scope

Delta intentionally avoids:
- Garbage collection
- Fully dynamic typing (static typing is always needed somewhere in the code)
- Massive standard library — you choose what you need

---

## 🔮 Future Considerations

- JIT mode for scripting use cases (optional)
- Native FFI support with C/C++ and Rust
- WASM backend

---

## 🧭 Development Status

This is a living spec. As of now:
- Syntax: Finished
- Parser: Planned via ANTLR → custom
- Compiler: High-level architecture defined
- Standard library: To be built from scratch, minimalist-first. Uses C standard library initially

Once stable, the full formal specification will move to its own repository as the Delta language hits its first self-hosted release.