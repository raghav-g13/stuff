Computer Achitectures Should Go Brrrr
Tesla AI HW
Talk by Eric Quinnell at BAR Seminar - 28 Aug 2024
@divBy_zero

Tesla Network Arch - Dojo Ethernet NIC

Intro - Arch should go brrrrr
    - Dumber design is smarter design
    - KEEP ISA and uARCH SIMPLE

    - Mojo 100 Gbps Dumb-NIC
        - RocE, Infinibad, TCP too complcated

RVC - Critique var len instructions
    - basic blocks - branch gap is longer now
    - ARMv8 went fixed width 64b bc Apple, forget 32b
    - RVC
        - Alignment - skid buffers + MUXes
            - Increase decode stage critical path and redirect latency
            - 3 cycle decodes are BAD
    - Permutes destroy chips
        - MUX select (connections) often on the critical path - very bad for timing and power 
    - Modern small nodes wire dominant, very high resistance, kill timing
        - Wires don't scale well
    - uOp caches are useless
        - hit rates are very very low - ~1%
        - spec doesn't catch
    - BTB coverage goes down as redirect targets at 16b v 32b
        - Jerry says 1 bit in address is not that expensive

RVV - uarch feasibility
    - IPC is not the right metric, this is DLP, elements processed per cycle
    - Applies to OoO too
    - Masks/Predicating affecting branch pred
    - Rename independent from SEW/LMUL/VLEN, insn cracking takes care of this
    - RISC v CISC argument
        - NEON ???? (read up) 

SPEC v JIT arch - P6 v Firestorm
    - LLVM - indirect threading garbage
    - stay < 2GHz, no uOp caches, no stupid SMT
    - Speedometer
    - Shit SW code, lots of indirecting branch threading - adapt HW

SMT bad for OoO, great for InO
Zen5 2-cycle scheduler is bad for back-to-back
    - TOO COMPLICATED

- AI writing better code bc infra maxed out, otherwise we're stuck w bad bad bad code.

- THINK ABOUT THE BRAIN/MEMORY
    - BIOMIMETIC COMP ARCH LOL

