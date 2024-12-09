# VHDL Counter with Overflow Bug

This repository demonstrates a common, subtle error in VHDL: an integer counter that doesn't correctly handle overflow. The original code (`counter.vhdl`) increments a counter without checking for the upper bound, leading to undefined behavior when the maximum value is exceeded.  The corrected code (`counter_fixed.vhdl`) addresses this issue.

## Bug Description

The `counter.vhdl` entity defines a simple counter. However, it lacks a mechanism to reset the counter after reaching the maximum value (7).  When the counter reaches 7 and increments, the result is undefined within the integer range specified.  This can lead to unpredictable behavior in simulation and synthesis.

## Solution

The `counter_fixed.vhdl` entity corrects the bug by adding a modulo operation. This ensures the counter wraps around to 0 after reaching the maximum value, providing the intended counting behavior.
