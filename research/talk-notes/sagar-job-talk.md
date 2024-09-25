Catch M(oo)re If You Can
Agile HW/SW Co-design for Hyperscale Cloud Systems
Talk by Sagar Karandikar at his Berkeley Job Talk - 4 Mar 2024

Cloud - abstraction
    - Infinite compute, storage, memory

1k Hyperscale Datacenters behind this cloud abstraction

One server
    - 10k - 100k Servers
    - 20 to 100+ MW
    - exabytes of storage

Exponential growth in demand (data, internet traffic)
Stagnation in supply (hardware scale)

Domain Specific HW
 - ML is a great suitable example
 - What about the rest?

Hardware (device) scaling = Moore's Law = What apps crave?
Let's do this with domain specific HW
    - compounding factor - full stack specialization 
    - doing this rapidly

Usability is key!

RTL sim is cycle exact, network/DRAM/IO Sim is cycle-level (really cycle-approximate)
FireSim can multiplex multiple cores (say 8) on an FPGA that fits only two cores

IDEA for internship lol: Write abstract FPGA models (transform w/ compiler?)

(Formal) Verification aspects => what properties are preserved between transforms (?)
    - Model behavior 
    - Model generation

Use profiling to:
 - Justifiy DSA existence
 - Influence DSA design
 - Publish data 
 - Build representative open-source benchmarks

Protobuf used for
 - RPC inter-service communication
 - Formatting data for storage

Stickyness in parts of the hyperscale stack

Hardening op/kernel =>>>> ensure consistent API

Getting the HW/SW interface right is important (static v dynamic info)

Need work in memory system, Smart NICs ... yeah

Compression acc: Enable more resource usage/tradeoff
    - explore combination of compression primtives

Software defined hardware
    - disaggregated trays of servers/chiplets w optical interconnects
    - sw manages these
    - reconstruct in sw the logical server abstraction
        - why not challenge this?

ChipNeMo - for berkeley infra 

Can we make communication easier/faster? 
