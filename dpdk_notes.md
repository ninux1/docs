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
1) librte_eal   = initializes pci, other hardware , os features environment variables. in kernel rte_eal_init initializes the EAL and allocates the memory from huge pages.
rte_mempool_create , creates the pool of mem bufs to hold the packet data.

DPDK models
1) Run to completion 
2) Pipeline

In run to completion I/O as well as application consuming those packets happen on single core however in the pipeline model the I/O happens on one core and those packets are then passed to the application running on a different core via ring buffers.   

Other parameters to consider for using DPDK in your architecture.
1) NUMA considerations, DPDK is NUMA aware. What memory are we using. Layouts.
2) Caching considerations, Cache miss is costly.
3) Transition look aside buffers, TLB is the cache of the page tables which are basically virtual to physical address mapping. So TLB caches the virt memory to physical memory page tables.
4) TLB misses are very costly.
5) Mapping of Virtual to physical memory = page table entry.
6) Multiple page table entries form page tables.
6) TLB is a cache for page tables.
7) If data is found in TLB its TLB hits else its a TLB miss which is nothing but a whole page walk which hits performance.
8) Alleviate the above scenario by using the Linux Huge pages.
9) Probability for finding a page address is higher in Huge pages than the smaller TLB's. i.e higher the huge page size, higher the probability of finding the page table address.
10) Better is to set the huge pages at the boot time.
11) rte_malloc is not lock free and should not be used in the data path i.e packet I/O
