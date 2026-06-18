# SV-UVM-2x1-MUX

## Overview

This project demonstrates the verification of a 2×1 Multiplexer using both traditional SystemVerilog testbench techniques and the Universal Verification Methodology (UVM).

The repository was developed to practice transaction-based verification, constrained-random stimulus generation, functional coverage, assertions, scoreboard-based checking, and reusable UVM testbench architecture.

## DUT Functionality

The 2×1 Multiplexer selects one of two input signals based on the select line.

| Select (s) | Output (y) |
| ---------- | ---------- |
| 0          | d0         |
| 1          | d1         |

Implemented functionality:

```systemverilog
y = (s) ? d1 : d0;
```

## Verification Features

### Non-UVM Testbench

* Transaction class
* Randomized stimulus generation
* Driver task
* Assertions
* Functional coverage
* Cross coverage
* VCD waveform generation

### UVM Verification Environment

* Sequence Item (Transaction)
* Sequence
* Driver
* Monitor
* Scoreboard
* Agent
* Environment
* Test
* Virtual Interface
* Constrained-random stimulus
* Functional coverage collection
* Automated result checking

## Coverage Model

Functional coverage is implemented using:

* Coverpoints for d0, d1, and s
* Cross coverage for all possible input combinations

Total cross combinations:

```text
d0 × d1 × s = 2 × 2 × 2 = 8 combinations
```

The goal is to achieve 100% functional coverage across all valid input combinations.

## Project Structure

```text
sv-uvm-2x1-MUX/
│
├── rtl/
│   └── mux_2x1.sv
│
├── non_uvm/
│   └── mux_tb.sv
│
├── uvm/
│   ├── mux_txn.sv
│   ├── mux_seq.sv
│   ├── mux_driver.sv
│   ├── mux_monitor.sv
│   ├── mux_scoreboard.sv
│   ├── mux_agent.sv
│   ├── mux_env.sv
│   ├── mux_test.sv
│   └── top.sv
│
└── README.md
```

## Simulation Results

* Randomized stimulus successfully exercised all DUT functionality.
* Scoreboard verified DUT outputs against expected results.
* Assertions detected protocol violations automatically.
* Functional coverage was collected and reported at the end of simulation.

## Tools Used

* SystemVerilog
* UVM 1.2
* QuestaSim / Riviera-PRO / EDA Playground
* EPWave

## Learning Outcomes

Through this project I gained hands-on experience with:

* SystemVerilog verification methodology
* Constrained-random verification
* Functional coverage
* Assertions
* UVM component hierarchy
* Transaction-based verification
* Scoreboard design and result checking

## Author

Shivaraj Hosad
M.Tech | Verification Engineer Aspirant
