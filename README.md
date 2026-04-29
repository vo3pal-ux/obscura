# 🌑 Obscura

**Obscura** is a high-performance, 9-layer Luau obfuscation engine designed specifically for the Roblox environment. It transforms readable source code into an encrypted, virtualized, and control-flow-flattened mess that is extremely resistant to static and dynamic analysis.

> [!IMPORTANT]
> This is a research project designed to push the boundaries of Luau bytecode virtualization and control-flow protection.

---

## 🛠️ Protection Layers

Obscura uses a multi-stage transformation pipeline to ensure that even if one layer is "cracked," the underlying logic remains protected.

1.  **Identifier Renaming**: Polymorphic renaming of all variables, functions, and parameters using randomized entropy.
2.  **String Encryption**: All literals are encrypted using a rotating XOR-based cipher and decrypted at runtime.
3.  **MBA (Mixed Boolean-Arithmetic)**: Transforms simple arithmetic into complex, logically equivalent boolean expressions.
4.  **Control Flow Flattening (CFF)**: Shatters the natural structure of functions into a state-machine based flat block.
5.  **Opaque Predicates**: Injects logic-based branches that are always true or always false but impossible for de-obfuscators to resolve statically.
6.  **Dead Code Injection**: Injects "junk" instructions that perform no action but confuse human readers and automated tools.
7.  **Table Indirection**: Wraps global and environment access in a proxy table system.
8.  **Anti-Tamper**: Runtime integrity checks that detect if the script's environment or source has been modified.
9.  **VM Virtualization (Layer 9)**: The "Gold Standard." Compiles your Luau code into a custom, randomized 16-bit bytecode and executes it via a stack-based interpreter.

---

## 🚀 Getting Started

### Prerequisites
- Python 3.10+
- A Roblox Studio environment for testing output.

### Installation
```bash
git clone https://github.com/vo3pal-ux/obscura.git
cd obscura
pip install -r requirements.txt
```

### Usage
To obfuscate a script with the full 9-layer stack (including the VM):
```bash
python main.py --input script.lua --output output.lua --vm
```

To use a specific seed for reproducible builds:
```bash
python main.py --input script.lua --output output.lua --seed 12345
```

---

## 🔬 Technical Overview: The Obscura VM

Unlike simple "constant-shufflers," the Obscura VM is a custom stack-based interpreter. 
- **16-bit Addressing**: Supports large-scale scripts with thousands of instructions.
- **Instruction Randomization**: Every build generates a new opcode mapping, making universal de-virtualization impossible.
- **Stack-Safety**: Implements strict stack management for table indexing, method calls (`self`), and variadic functions.

---

## 📜 License
Distributed under the MIT License. See `LICENSE` for more information.

---

## ⚠️ Disclaimer
Obscura is intended for educational purposes and protecting intellectual property in the Roblox ecosystem. Use responsibly.
