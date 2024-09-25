Enabling Full-Stack DNN Accelerator Design and Evaluation
Dissertation Talk by Hasan Genc

Motivation
* Workload Diversity
    * Model archs - CNN (high compute intensity) v LLMs
    * arithmetic involved
    * Sparsity & Compression
* Environmental Diversity
    * Small Edge v Big Edge (cars) v Cloud v SC 
* Architecture Diversity
    
Challenges
    * Accelerator Design - Stellar
    * Acc Integration - Gemmini

Gemmini:

Full-System Visibility
    * Memory Hierarchy - caches, vm, etc.
    * Host CPUs - esp unsupported kernels
    * OS

Gemmini exposes three levels of prog interfaces
    * ONNX
    * C libs
    * ISA instrs

Case Studies:

How Does VM Affect overall DNN Perf?
    * two-level TLBs
    * very bursty
    * private TLBs very impactful
        * Added L0 TLB for same page reqs
    
Memory-Partitioning for multi-acc SoCs
    * Private scratchpads for unicore - conv layers
    * Shared L2 better for dual core - residual adds

Stellar - Designing and Synthesizing Dense and Sparse Accelerators
    
Dataflow Taxanomy
    * Weight Stationary v Output Stationary
    * How inputs and outputs flow?

Separation of Concerns
    * Functional behavior
    * Dataflow - Space-Time Transforms - generally linear affine as it is easy to reason about while covering a large portion of the design space
    * Formats
    * Load-balancing

Hardware Generation of Spatial Arrays - COOL!
    * Generate tensor-iteration space
    * Map to dense physical arrays
    * Prune PE-to-PE connections
    * scratchpads, regfiles, load-balancers generated from parameterizable RTL templates that are v simple and general
    * Optimization passes for diff components

    * Limitations
        * Affine reductions much easier than tree/recursive reductions - blur lines between separation of concerns

* Time mgmt
* Group brainstorm - surround yourself w good people
* Student => Senior Student
* Don't put your life on hold, don't treat it as a transitional phase
    * treat like a job

