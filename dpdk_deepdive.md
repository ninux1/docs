Achieving a line rate of 40 G or higher in DPDK is a collective effort of multiple factors and not just one.
In DPDK 
1) packet capture is changed from Interrupt driven to polling.
2) Network kernel driver now run in usermode.
3) Kernel scheduler is replaced by CPU pinning/pthread affinity.
4) Huge pages are used in place of 4K paging.
5) using lockless intercore communication.
6) 
