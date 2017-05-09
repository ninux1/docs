
Full, Partial OR Para Virtualization defines the way virtual machines interact with the hardware.
KVM, VMware ESX/ESXi servers totally depends on hardware compatibility They work only on hardware which supports Virtualization at 
hardware level.

In partial virtualization only some parts of the hardware can be virtually simulated so that they can be used as real hardware for VM’s.

In Paravirtualization, Virtualization is implemented where your Hardware is not at all supported.

By using para-virtualization we have to create domains so that VM works in simulated environment without direct interaction of 
actual hardware. XEN is good example of this type of Virtualization. XEN creates it’s own domains to isolate VM's from the hardware.
