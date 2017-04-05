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
* sudo ovs-ofctl -O Openflow13 add-flow vbr priority=500,in_port=2,actions=output:3
* sudo ovs-ofctl -O Openflow13 add-flow vbr priority=500,in_port=3,actions=output:2
* sudo ovs-ofctl -O Openflow13 add-flow vbr priority=32768,action=drop
* sudo ovs-ofctl -O Openflow13 dump-flows vbr
* sudo ovs-ofctl -O Openflow13 show vbr 
* sudo ovs-vsctl set bridge vbr protocols=OpenFlow13
* sudo ovs-vsctl set-controller vbr tcp:192.168.56.102:6633
* sudo ovs-vsctl set-controller vbr connection-mode=out-of-band
* sudo ovs-vsctl del-controller vbr
* -------------------------------------------------------------
* sudo modprobe openvswitch
* sudo ovsdb-server --remote=punix:/usr/local/var/run/openvswitch/db.sock --remote=db:Open_vSwitch,Open_vSwitch,manager_options --private-key=db:Open_vSwitch,SSL,private_key --certificate=db:Open_vSwitch,SSL,certificate --bootstrap-ca-cert=db:Open_vSwitch,SSL,ca_cert --pidfile --detach --log-file
* sudo ovs-vsctl --no-wait init
* sudo ovs-vswitchd --pidfile --detach --log-file
* -------------------------------------------------------------






