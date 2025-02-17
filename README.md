# VHDL Sensitivity List Error

This repository demonstrates a common error in VHDL code related to the sensitivity list of a process.  The `wrong_sensitivity.vhdl` file contains a process with an incomplete sensitivity list, causing unexpected behavior. The correct implementation is shown in `correct_sensitivity.vhdl`.

## Problem

In the `wrong_sensitivity.vhdl` file, the process only includes 'clk' and 'a' in its sensitivity list.  This means the process will only execute when 'clk' or 'a' changes. However, the output 'c' depends on both 'a' and 'b'. If 'b' changes while 'clk' and 'a' remain constant, the output 'c' will not be updated correctly.

## Solution

The `correct_sensitivity.vhdl` file shows the corrected code. The sensitivity list now includes 'b', ensuring that the process executes whenever 'clk', 'a', or 'b' changes. This fixes the unexpected behavior and guarantees the correct functionality of the design.

## How to reproduce the error

Compile and simulate both files.  Observe the difference in behavior when 'b' changes independently of 'clk' and 'a'.