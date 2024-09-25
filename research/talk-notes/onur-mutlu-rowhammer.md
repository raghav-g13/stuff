RowHammer, RowPress & Beyond
Talk by Onur Mutlu at BAR Seminar - 28 Feb 2024

- Rowhammer - inducing bitflips - getting worse
    - Hammer one row with pre-charges, corrupt neighboring rows - density of cells matters
    - cell-to-cell coupling/interference
    - Every cell reacts differently to temp

- Need reliable platforms - perf, efficiency , and SECURITY

- Memory scaling not going well
    - As memory scales, it gets more reliable
    - Newer generations are even more vulnerable

- Changed FPGAs to swap out mem controller - soft mem controller (SoftMC) to study impact of various ops and features

- Don't need to refresh all DRAM cells as often
    - Dependent on location, time, stored value pattern

- Insert bitflips in PTEs
    - Change your access perms
    - Change pages you're able to access
- Attack neural nets which make decisions

- Industry can do the following
    - increase refresh rates
    - adaptively throttle accesses to hammered row and increasingly refresh neighboring rows

- DRAM controllers do row re-mapping

- Hard Disks, SSDs (eg NAND Flash) already have intelligent controllers
    - Can we make them faster and smaller?

- Effects of aging? Persistent attacks? Environment?

- Proposed solution - TRR and retaliatory attack - TRRespass
    - TRR - Target Row Refresh - not well specified
        - overflow the tables that maintain TRR state

Google - Half Double RowHammer
    - Make defence mechanism an attack

Microsoft - RowHammer using coherence traffic (damn kinda creative) 

SK Hynix - Access counts per row + more intelligent controller
    - Onur doesn't think this is complete
    - Need more adaptive thresholds at least

RowPress 
    - New disturbance phenomenon
    - Activate DRAM row for a long time
    - inc with temp
    - Access many cache lines from same row to keep row open

Future
    - Rethink interface between and memory
    - Be "principled"
    - Online testing and patching in field

- Interesting Papers
    - Physical fault injections - Induce mem errors  - to attack a virtual machine
        RowHammer replaced physical with software fault injection

- What about device level intervention? Since this has been going on for ages now ...
