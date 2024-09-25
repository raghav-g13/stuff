AWS Trainium
Talk by Nafea Bshara  at BAR Seminar - 28 Feb 2024

Cloud DSA

* Nitro
* Graviton
* Inferentia
* Trainium

Trainium
    * These chips are massive
    * Neuron - compiler, collectives (data transfer b/w devices) on-chip and off-chip network, profiler, debugger

- Don't make devs re-optimize

* HBM
* Core
    * Big systolic array - tensor engine - very power and area efficient
    * "Scalar" engine
    * TCM
    * Vector
        * double digit instances of 512b wide "SIMD"
    * GpSIMD Engine

Compiler v Hardware Roles - For a "classic" / DSP CPU
    * Rapidly evolving workloads
    * Put more stuff in compiler / sw

HW - Muscle
    * "Supercharged" VLIW CISC
        * Every instr is 200-500 cycles
    * Programmable control path w ucode (programmable - can extend ISA)

Datatype
    * C-FLOAT
        * Configurable float
        * different layers/passes might benefit from different range v precision

VLLMs
    * at very large model sizes, while the compute/mem ratio varies, other requirements (arithmetic, network) remains quite similar between training and inference
 
(Probablistic) Stochastic rounding - in-silicon tricks
    * After ALU op

How are compiler level decisons made for so many knobs (say different datatypes)

Sparsity
    * N:K sparsity - structured
    * 16:4 better than 2:1

Distributed Training
    * Data parallelism was okay for smaller models
        * As you go wider, need more epochs to train
        * Poor strong scaling (?) behavior
    * Model parallelism
        * all to all comm needs high bw, low latency interconnect
    * ~13 Tbps network bw
    * Direct NIC <=> Trainium bus + RDMA + SRD [no TCP (too much overhead)]
        * SRD: Transport layer protocol

Collective
    * two level interconnect (within chip and inter-chip ig? or two-level inter-chip?)

Compiler
    * Use HLO IR from XLA
    * Based on LLVM
    * Have coarser block-sparsity support here

Ease of Use
    * JIT compile existing models to Trainium

Neuron Kernel Interface
    * bare-metal language to insert "custom" instrs

Bora: Some startups wants to manke model-specific chips every 6 months - wtf?! 
    
