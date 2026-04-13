# UVM-Based Verification of 4-bit ALU

## 📌 Overview
This project implements a **UVM (Universal Verification Methodology)** testbench in SystemVerilog to verify a 4-bit Arithmetic Logic Unit (ALU). The design supports multiple operations controlled by an opcode, and the verification environment focuses on **constrained-random testing, functional coverage, assertions, and scoreboard-based checking**.

---

## 🎯 Objectives
- Verify functionality of a 4-bit ALU for multiple operations  
- Build a complete UVM testbench architecture  
- Apply constrained-random and directed testing  
- Track verification completeness using functional coverage  
- Validate correctness using assertions and scoreboard  

---

## 🧠 ALU Design

### 🔹 Supported Operations

| Opcode | Operation |
|--------|----------|
| 000 | ADD |
| 001 | SUB |
| 010 | AND |
| 011 | OR  |
| 100 | XOR |
| 101 | NOT (A) |
| 110 | Shift Left |
| 111 | Shift Right |

---

## 🏗️ UVM Testbench Architecture
Test
└── Environment
├── Agent
│ ├── Driver
│ ├── Monitor
│ └── Sequencer
├── Scoreboard
└── Coverage


---

## ⚙️ Tools & Technologies
- **SystemVerilog**
- **UVM 1.2**
- **QuestaSim / ModelSim**
- Optional: **EDA Playground**

---

## 🔄 Verification Flow
1. **Sequence** generates randomized and directed transactions  
2. **Driver** applies inputs (`a`, `b`, `op`) to DUT  
3. **Monitor** captures DUT outputs (`result`, `carry`)  
4. **Scoreboard** computes expected results and compares outputs  
5. **Coverage** collects functional metrics  

---

## 🔍 Features Implemented

### ✅ Constrained Random Testing
- Randomized inputs (`a`, `b`, `op`)  
- Ensures broad input space coverage  

### ✅ Directed Testing
- Targeted scenarios for each opcode  
- Edge cases like all-zeros and all-ones  

### ✅ Functional Coverage
- Coverpoints on opcode and operands  
- Cross coverage (`op × a × b`)  
- Achieved **~80% functional coverage**

### ✅ Assertions (SVA)
- Operation-specific correctness checks  
- Ensures real-time validation of DUT behavior  

### ✅ Scoreboard-Based Checking
- Golden reference model implemented  
- Detects mismatches between DUT and expected results  

---

## 📊 Sample Output
UVM_INFO [SCB] PASS
UVM_ERROR [SCB] FAIL op=...
==== COVERAGE ====
Coverage = 80.00 %


---

## 🧪 Key Test Scenarios
- Arithmetic operations (ADD, SUB with overflow/underflow)  
- Logical operations (AND, OR, XOR)  
- Unary operation (NOT)  
- Shift operations (left/right)  
- Edge cases (all zeros, all ones)  

---


---

## 🧪 Key Test Scenarios
- Arithmetic operations (ADD, SUB with overflow/underflow)  
- Logical operations (AND, OR, XOR)  
- Unary operation (NOT)  
- Shift operations (left/right)  
- Edge cases (all zeros, all ones)  

---

## 📈 Key Learnings
- UVM component hierarchy and phase execution  
- Transaction-level modeling (TLM communication)  
- Importance of functional coverage in verification  
- Debugging using scoreboard and waveform analysis  
- Assertion-based verification (SVA)  

---

## 🚀 Future Enhancements
- Achieve higher coverage through coverage closure techniques  
- Add assertion coverage reporting  
- Extend ALU to parameterized width  
- Introduce error injection and robustness testing  

---

## 👤 Author
**Harsh Pandey**  
VLSI Design & Verification Enthusiast
