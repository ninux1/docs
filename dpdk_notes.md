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


