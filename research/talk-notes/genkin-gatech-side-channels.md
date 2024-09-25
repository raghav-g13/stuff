Side Channel Attacks: Lessons Learned or Troubles Ahead?
Talk by Daniel Genkin (Georgia Tech) at BAR Seminar - 13 Mar 2024

Evolution of Side Channel Attacks (AS DANIEL SEES IT)
    * 2005-16: Classic Cache Timing for cryptographic hashing/keys
    * 2017-18: Spectre/Meltdown/Foreshadow - Systems and Kernel
        * Speculative & Transient Execution Attacks
    * 2019-now: Okay everything, everywhere, all at once

    * 90s-2k10s: People moved between computers
    * 10s-20s: Computers move with people
    * Now: Lots of specialization
    
Overflows using negative indices
Apple Watch Series 1 doesn't have a branch pred - not vuln to Spectre

* We don't have a clear solution to Spectre
* No more follow-up attacks, no exploits
* What's happening?

* Everything in the browser
    * They have secrets - one of the most trusted components of a computing system
    * Tabs live in same process
        * Chrome changed that - Site isolation
            * Fixed? Nope.
                * Spectre is not about arrays. More than that!
        * Safari => iLeakage

Site Isolation in Safari
    * Too many tabs for individual procs
    * One process per tab
    * Until out of memory
    * Federated logins require call backs which are cross-process
        * Safari has no IPC
    * Put in the same space whenever window.open
        * Too many pieces of third-party embedded content like federated login

Other countermeasures:
    * Side channel: Take away timers
        * Is the timer really necessary?
        * Can use race conditions an identify using which path taken - Concurrency
    * Sandboxing countermeasures: Try reading out of bonds?
        * Use 4GB address spaces and 32b pointers
        * `base_ptr` is internal 64b value in C++, not a property in JS
        * Throw off by creating own datatype, fail type check but make it too long (L3$ miss) + branch pred predicts type check as taken
            * Speculative type confusion
            * Can't disable branch pred on type checks because that is too slow
            * Read arbitrary pointers
    * Reliability 
        * Speculative exception supression
            * Wrap attack inside mispredicted if
    

Designing a speculatively type system

Research is food motivated LOL

Microarchitectural Software Optimization
    - Optimize per arch
    - PGO is more limited in scope and dont on the fly
