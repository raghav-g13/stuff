Modular Abstractions for Hardware Design
Talk by Rachit Nigam at his Berkeley Job Talk - 4 Mar 2024

SW/HW abstraction/decomposition
    - Drive hw/sw improvements independently
    - Relax/modify abstractions for better programmability (CUDA)

Filament - a language for modular hw design
    - Reusable "hw" packages

Adder v Multiplier
    - Missing info on timing of "package"
    - Thus can't be modular, need to build against impl
    - So? Use latency insensitive interface
    - Now have dependencies between valid and out signals - capturing timing 
    - Existing HDLs don't capture module timing behavior

eg. Memory Management abstracted away from C++ to Java
    Rust and how filament is the same for HW design

Efficiency cost of abstractions!!! But HW wants to be fast(est)

Filament
    - Captures timing behaviors
    - Invocation schedules the execution of some hardware block with some inputs
        - Hardware reuse
    - Scheduling expressions only allow statically-scheduled hw
        - input independent latency
    - Read output from invocation
    - Actionable feedback
    - It is a structural lang (not behavioral) - lowest level of abstraction
    - **Well-typed programs only read from semantically valid signals**
    - Compile time resource reuse conflict errors
    - **Well-typed programs do not have any resource conflicts**

Filament as an integration language

- Parameterized design
    - Compile time symbolic reasoning for all possible points in param space
    - Can affect timing behavior

Latency Insensitive Circuits
    - WIP
Show deadlock avoidance 
    - WIP

Calyx - compiler infra - ecosystem of langs
    - Alt to LLVM - strength is its IR
    - High level langs to circuits
    - groups of circuit "ops" to show when things are done
    - done break down into computations
        - switch between parallel hw and sequential hw

Abstraction in user schedulable langs like Exo

Ecosystem for hardware design (dyn interfaces) in Short Term
Can we build pd metrics into langs? in Short Term

Rethinking HW tools - Long Term
Programmable Accelerators - Long Term

Calyx isn't tied to particular arch whereas HLS is often tied to specific arch
    - Pushing burden for info on user to incr amount of possible optmization 

Tower of compilers

