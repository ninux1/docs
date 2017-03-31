* sudo ip link add type veth
* sudo ip netns add <>
* sudo ip link set veth0 netns <>
* sudo ip netns exec node1 /bin/bash
* sudo ip netns exec node2 ifconfig veth2 up
