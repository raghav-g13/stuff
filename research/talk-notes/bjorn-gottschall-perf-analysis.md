ARM Norway / NTNU / Ghent
Talk by Bjorn Gottschall at BAR Seminar - 2 Oct 2024

Time-Proportional Performance Analysis for OoO Processors

- Chips are power-limited - wasting power is wasting perf
- Perf analysis is imp

Perf Analysis (particularly for Perf Critical portions)
    - What takes time?
    - Why does it take time?
 
- Attributing execution time to insts/basic blocks is hard

- Statistical sampling enables measuring whole execution w low overhead
- Time proportional helps with attribution

Statistical Sampling
    - infrequently inspect running inst
    - build runtime distribution
    - more samples = closer to golden ref

Time Proportional
    - The prob of sampling should be propotional to inst's share of execution
    - Unfortunately, lots of bias

Systematic Bias
    - Where are you measuring?

RG: PERF ANALYSIS IS A VERY INTERESTING AREA
    - (So this is a great talk haha)
    - Can we evade/elide time proportionality?
    - Can we build towards stronger guarantees 

Systematically inaccurate and cannot be time-proportional
    - SW like Linux Perf - Prog Counter Inst Profilers
    - Xilinx TCF - Last Committing Inst Profilers
    - Intel PEBS - Next Comitting Inst Profilers

Sample at Commit!
    - Latencies unknown in fetch / frontend
    - Latencies hidden in backend
    - Instructions past commit lose latencies
    - Inst latencies exposed at commit

Use shares of sample going to each instr - account for ILP

How do we get ground truth / Golden Reference?
    - LOTS OF TRACE DATA, trillion instrs, O(PB) data

Time-Proportional Event Analysis

Per-Instr Cycle Stacks
    - Atrribute inst exectuion time to events such as $/TLB misses, branch mispredicts

SOTA
    - Event vector in PMU w tagged events
    - FE tag profiler like AMD IBS tags the wrong instr for an event

TEA
    - Per instr event vector
    - Sample the vector at commit
        - Event vector is now complete
    
TraceDoctor
    - Highly efficient tracing interface

RG: Ask Bjorn about overheads
