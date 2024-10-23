MIT
Talk by Srini Devadas at BAR Seminar - 16 Oct 2024

Designing Hardware for Cryptography and Cryptography for Hardware

Time-Proportional Performance Analysis for OoO Processors

Influence cryptographers to design protocols for hw?

Encryption everywhere => AES-NI (and hw-accelrated AES in general has good perf)

There are lots of crypto problems. But building accelerators for them is boring.

Verfiable Comuputation and ZKPs
    - Proving time >> Computing f(x) > Verifying result
    - Zero Knowledge often due to privacy
        - Prover can provide secret inputs to f, client cannot execute themselves
    - FHE is different that client has secret, server performs compute

Prove ML model is fair or smth

Groth16
    - Popular ZKP scheme bc tiny proofs
    - Compute bound (CHECK!)
        - elliptic curve 
        - many many large multiplies

ZKSnark - library for modular ZKPs combining IOPs (turn proof into polynomial) and PCS (prove on polynomial?)

PCS
    - Lattice & Curve are too mathematically complex
    - Hash - design for this

Q: How do you access if you're control bound?

Constrain these problems to a particular structure and then express that structure (say as SpMV)
Design/use hw for that structure
    - What's Benes network and NTT?
    - Changed ECC protocol used
        - worse asymptotically but better in this case 
            - asymptotics might not always practically apply, consts matter too

Sumcheck used for verification by testing at many random points
    - recomputation v caching

Look at recording for all involved tasks + units, how they improve on diff tasks, sizes of diff units

LOL they don't trust their own numbers

