# What-eats-my-server
Curated list of things to check for troubleshooting 

## Table of Contents

- [Hardware]()
    * CPU
    * Memory
    * Load
    * Disk
- [Journalctl]()
- Network

## Hardware

### CPU
*First:* Using `lscpu` command, We're going to see how want CPUs we have:

    $ lscpu
    Architecture:          x86_64
    CPU op-mode(s):        32-bit, 64-bit
    CPU(s):                4
    Thread(s) per core:    2
    Core(s) per socket:    2
    CPU socket(s):         1
    NUMA node(s):          1
    Vendor ID:             GenuineIntel
    CPU family:            6
    Model:                 37
    Stepping:              5
    CPU MHz:               2667.000
    Virtualization:        VT-x
    L1d cache:             32K
    L1i cache:             32K
    L2 cache:              256K
    L3 cache:              3072K
    NUMA node0 CPU(s):     0-3

In the above my Intel i5 laptop has 4 "CPUs" in total

> CPU(s):                4

of which there are 2 physical cores

> Core(s) per socket:    2

of which each can run up to 2 threads

> Thread(s) per core:    2

at the same time. These threads are the core's logical capabilities.

**Intel refers to a physical processor as a socket.**

From `man lscpu`:

   > CPU<br>
   The logical CPU number of a CPU as used by the Linux kernel.<br>
   CORE<br>
    A core can contain several CPUs.<br>
   SOCKET<br>
   A socket can contain several cores.<br>

https://unix.stackexchange.com/a/279354/123625

### Disk
https://unix.stackexchange.com/questions/125429/tracking-down-where-disk-space-has-gone-on-linux
https://unix.stackexchange.com/questions/113840/whats-eating-my-disk-space

## Journalctl
https://superuser.com/a/1188380/760542

## Network
Knowing what serivce lestining on a port
`ss -plnt 'sport = :80'`

