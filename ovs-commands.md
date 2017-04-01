* sudo ip link add type veth
* sudo ip netns add <>
* sudo ip link set veth0 netns <>
* sudo ip netns exec node1 /bin/bash
* sudo ip netns exec node2 ifconfig veth2 up
* ovs-vsctl add-br ovs-switch
* ovs-vsctl add-port ovs-switch veth1
* ovs-ofctl add-flow of-switch "in_port=LOCAL,table=0,idle_timeout=60,ip,hard_timeout=60,vlan_tci=0x0000,dl_src=78:2b:cb:4b:db:c5,dl_dst=00:09:8a:02:80:c0, nw_proto=1,nw_dst=192.168.1.100, n w_src=192.168.7.189,actions=drop"
* sudo ip netns add red
* sudo ip netns add blue
* sudo ip link set veth0 netns red
* sudo ip link add type veth
* sudo ip link set veth2 netns blue
* sudo ovs-vsctl add-br switch
* sudo ovs-vsctl add-port switch veth1
* sudo ovs-vsctl add-port switch veth3
* sudo ovs-vsctl del-port switch veth3
