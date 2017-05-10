Dpdk is a set of data plane libraries and network interface controllers.

Problems which dpdk addresses
	Packet reception cant keep up with the amount of interrupts for the reception of the packets.
	Lot of overhead for the linux scheduler to task switch.
	Access to the shared data structures becomes bottleneck.
	Lot of TLB thrashing.

Packet processing thread is given exclusive access to the cpu core so that it can have dedicated resource for packet processing.

Set processor core affinity so that it gets the dedicated core for packet reception OR Pakcet transmit.

DPDK is a set of userspace software libraries.

Network device drivers for NICs supported in DPDK run in Linux userspace. They are also known as Poll Mode Drivers. PMD.


Below optimization technologies/primitives are used for Intel DPDK on Intel Arch.
1) Hugepages
2) PreFetching/Software prefetching
3) Intel DDIO Direct Data I/O
4) Cache Alignment
5) New 
6) Memory interleave
7) pthreads and affinity
8) NUMA
9) Memory channel Use


DPDK libraries
1) librte_eal   = initializes pci, other hardware , os features environment variables.

DPDK models
1) Run to completion 
2) Pipeline

In run to completion I/O as well as application consuming those packets happen on single core however in the pipeline model the I/O happens on one core and those packets are then passed to the application running on a different core via ring buffers.   
