How to run:
```
python3 network_tester.py -nl 32 -p 0.5
```
nl is the number of Processing Elements, and P is the Rent exponent. 
For instance, the switch configuration is:
- p==1: pi-pi-pi-pi ...
- p==0.5: pi-t-pi-t ...

You need iverilog to run the simulation.

---
This is a deflection-routed Butterfly-Fat-Tee NoC generator used in "Reducing FPGA Compile Time with Separate Compilation for FPGA Building Blocks" (FPT 2019), "PLD: Fast FPGA Compilation to Make Reconfigurable Acceleration Compatible with Modern Incremental Refinement Software Development" (ASPLOS 2022), "REFINE: Runtime Execution Feedback for INcremental Evolution on FPGA Designs" (FPGA 2024), and others. In the aforementioned works, non-pipelined versions are used. 

With pipelined registers enabled, BFT NoCs easily achieve >700MHz in Versal or Ultrascale Plus FPGAs. For example, BFT-32 (rent P = 0.5, one additional pipeline stage, package size = 32b, ~90K LUTs) achieves **814-847MHz** in Versal -3HP when implemented out-of-context with Vivado 2026.1. Make sure to do timing-driven synthesis. Credit goes to Nevo Magnezi.
