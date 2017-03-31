* apt-get remove openvswitch-common openvswitch-datapath-dkms openvswitch-controller openvswitch-pki openvswitch-switch
* cd openvswitch-<Version>/
* ./configure --prefix=/usr --with-linux=/lib/modules/`uname -r`/build
* make
* make install
* make modules_install
* rmmod openvswitch
* depmod -a

* modprobe openvswitch

* /etc/init.d/openvswitch-switch start



