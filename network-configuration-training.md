#### 用路由器二层接口 配置 telnet


```
telnet 192.168.0.6 6001

system-view
sysname yingshaoxo

vlan 10
quit

interface Ethernet0/0/1
port link-type access
port default vlan 10
quit

interface vlan 10
ip address 192.168.1.31 24
quit

aaa
local-user manager password cipher hi
local-user manager privilege level 15
local-user manager service-type telnet
quit

user-interface vty 0 4
authentication-mode aaa
quit
```

-------------------------------------

cipher
暗号

vty
Virtual teletype
___

#### 交换机使用 sftp


```
telnet 192.168.0.6 6007

//let's assume the vlan10 at switch is 192.168.1.31
//start sftp at 192.168.1.32

tftp 192.168.1.32 put vrpcfg.zip

tftp 192.168.1.32 get vrpcfg.zip yingshaoxo.zip
```

---------------------------------------

#### 端口属性设置


```
telnet 192.168.0.6 6004

//Let's assume that we already have two switches connected by a line at each Ethernet0/0/1

display interface Ethernet 0/0/1
system-view
sysname yingshaoxo
interface Ethernet 0/0/1
undo negotiation auto
duplex half
speed 10

vlan 10
quit
interface Ethernet 0/0/1
port link-type access
port default vlan 10

interface vlan 10
//Let's assume another switch have an ip address 1.1.1.6
ip address 1.1.1.7 24

ping 1.1.1.6
```

-----------------------------

#### 端口隔离配置


```
telnet 192.168.0.6 6004

// Three PC connect to one switch, Ethernet0/0/1, 2, 3

system-view
sysname yingshaoxo
port-isolate mode l2

interface Ethernet 0/0/1
port-isolate enable
port link-type access
quit

interface Ethernet 0/0/2
port-isolate enable
port link-type access
quit

//set three PC ip address directly from PC itself with 192.168.1.1, 2, 3
//now PC1 can't ping PC2 successfully
```

--------------------------------

#### 端口聚合


```
telnet 192.168.0.6 6004
system-view
sysname SwitchA

//make sure to reset every Ethernet 0/0/*
reset saved-configuration
reboot

interface eth-trunk 1
//bridge protocol data units
bpdu enable 
mode lacp-static
quit

interface Ethernet 0/0/1
eth-trunk 1
quit

interface Ethernet 0/0/2
eth-trunk 1
quit

interface Ethernet 0/0/3
eth-trunk 1
quit

lacp priority 100

interface eth-trunk 1
max active-linknumber 2
quit

interface Ethernet 0/0/1
lacp priority 100
quit

interface Ethernet 0/0/2
lacp priority 100
quit

interface Ethernet 0/0/3
lacp priority 100
quit

display eth-trunk 1

interface eth-trunk 1
lacp preempt enable
lacp preempt delay 10

display eth-trunk 1

interface Ethernet 0/0/2
shutdown
quit

display eth-trunk 1

interface Ethernet 0/0/2
undo shutdown
quit

display eth-trunk 1
```

___

Aggregation
聚合

lacp
Link Aggregation Control Protocol

preempt
抢占

---

MSTP的配置


```
// for SwitchA
system-view
sysname SwitchA
stp mode stp

// for SwitchB
system-view
sysname SwitchB
stp mode stp

// for SwitchC
system-view
sysname SwitchC
stp mode stp

// for SwitchD
system-view
sysname SwitchD
stp mode stp

// A
stp root primary

// D
stp root secondary

// C
interface ethernet 0/0/1
stp cost 20000
quit

//B
interface ethernet 0/0/2
stp disable
quit

//C
interface ethernet 0/0/2
stp disable
quit

//A,B,C,D
stp enable

//A
interface ethernet 0/0/1
bpdu enable
quit
interface ethernet 0/0/2
bpdu enable
quit

//B
interface ethernet 0/0/1
bpdu enable
quit
interface ethernet 0/0/3
bpdu enable
quit

//C
interface ethernet 0/0/1
bpdu enable
quit
interface ethernet 0/0/3
bpdu enable
quit

//D
interface ethernet 0/0/1
bpdu enable
quit
interface ethernet 0/0/2
bpdu enable
quit
```

-----------------------

跨交换机 VLAN 的配置


```
telnet 192.168.0.6 6004
system-view
sysname SwitchA

vlan 3
quit
interface ethernet 0/0/1
port link-type access 
port default vlan 3
quit

interface ethernet 0/0/2
port link-type trunk
port trunk allow-pass vlan 3

// SwitchB do the same thing
```

-------------------------

GVRP(generic VLAN Registration Protocol) 配置


```
telnet 192.168.0.6 6005
system-view
sysname Boss

gvrp

interface ethernet 0/0/1
port link-type trunk
port trunk allow vlan all
bpdu enable
gvrp
quit

interface ethernet 0/0/2
port link-type trunk
port trunk allow vlan all
bpdu enable
gvrp
quit

display vlan
```

-------------------------------

三层独臂路由器让下面不同的VLAN互通


```
telnet 192.168.0.6 6003
system-view
sysname Boss

Interface GigabitEthernet 0/0/0.1
dot1q termination vid 100
ip address 10.31.10.1 255.255.255.0
arp broadcast enable
quit

Interface GigabitEthernet 0/0/0.2
dot1q termination vid 200
ip address 10.31.20.1 255.255.255.0
arp broadcast enable
quit

//PC1, 10.31.10.2
//PC2, 10.31.20.2
```

-------------------------------

三层交换机的静态路由配置



```
//B
system-view
vlan 20
quit
interface ethernet 0/0/3
port link-type access
port default vlan 20
quit
interface vlan 20
ip address 1.1.2.1 255.255.255.0
quit

vlan 40
quit
interface ethernet 0/0/1
port link-type trunk
port trunk allow-pass vlan all
quit
interface vlan 40
ip address 1.1.4.2 255.255.255.0
quit

vlan 50
quit
interface ethernet 0/0/2
port link-type trunk
port trunk allow-pass vlan all
quit
interface vlan 50
ip address 1.1.5.2 255.255.255.0
quit

//A
system-view
vlan 10
quit
interface ethernet 0/0/2
port link-type access
port default vlan 10
quit
interface vlan 10
ip address 1.1.1.1 255.255.255.0
quit

vlan 40
quit
interface ethernet 0/0/1
port link-type trunk
port trunk allow-pass vlan all
quit
interface vlan 40
ip address 1.1.4.1 255.255.255.0
quit

//C
system-view
vlan 30
quit
interface ethernet 0/0/2
port link-type access
port default vlan 30
quit
interface vlan 30
ip address 1.1.3.1 255.255.255.0
quit

vlan 50
quit
interface ethernet 0/0/1
port link-type trunk
port trunk allow-pass vlan all
quit
interface vlan 50
ip address 1.1.5.1 255.255.255.0
quit

//PC1: 1.1.1.2/24
//PC2: 1.1.2.2/24
//PC3: 1.1.3.2/24

// set routing table
// A
ip route-static 1.1.2.0 24 1.1.4.2
ip route-static 1.1.5.0 24 1.1.4.2
ip route-static 1.1.3.0 24 1.1.4.2

// B
ip route-static 1.1.1.0 24 1.1.4.1
ip route-static 1.1.3.0 24 1.1.5.1

// C
ip route-static 1.1.2.0 24 1.1.5.2
ip route-static 1.1.4.0 24 1.1.5.2
ip route-static 1.1.1.0 24 1.1.5.2

// 3 PC has to set gateway, for example, PC1, 1.1.1.1, 1.1.2.1, 1.1.3.1
```

![](/assets/switch_static_routing.png)

---

按理来说，我们可以从这一系列的操作中学到很多东西。

1. PC1 到 SwitchA，设置了一个 access port
untagged frame 通过贴上 pvid，变成了 vlan10 tagged frame

2. SwitchA 到 SwitchB，设置了两个 trunk port
在第一个端口，`vlan10 tagged frame`与`默认的pvid 1`不同，被直接发送；在第二个端口，`vlan10 tagged frame` 属于 `allowed vlan`，所以被接收

3. SwitchB 到 PC2，设置了一个 access port
把`vlan10 tagged frame`变成`untagged frame`，再发送给 PC2

___

DHCP(Dynamic Host Configuration Protocol) 配置


![](/assets/DHCP configure.png)

//// DHCP server
system-view
dhcp enable

//set a ip pool, from 192.168.31.1 to 192.168.31.253
ip pool 1
network 192.168.31.0 mask 255.255.255.0
dns-list 202.102.4.141
gateway-list 192.168.31.254
lease day 2
quit

//make sure all frames to pc is untagged, all frames to DHCP server is tagged with vlan 10
vlan batch 10
interface Ethernet 0/0/1
port hybrid pvid vlan 10
port hybrid untagged vlan 10
quit

// the DHCP Server has to have an ip_address, so other host could reach it.
interface vlanif 10
ip address 192.168.31.1 24

// and we also have to allow/enable that dhcp protocol forwarding at the output port (here is a virtual LAN)
dhcp select global

---------------------

VRRP 配置 (目的: 让各个Host通过IP互通)


//// A, B, C
system-view
undo stp enable
y

// set Host gateway
//hostA: 10.1.1.111
//hostC: 10.1.1.112
//hostB: 20.1.1.1

//// A
system-view
vlan batch 100 200
interface ethernet 0/0/1
port hybrid pvid vlan 100
port hybrid untagged vlan 100
// the function of hybrid is when you send vlan100 frame, it convert it to untagged frame; when you receive untagged frame, it will convert it to vlan100 tagged frame
quit

interface vlan 100
ip address 10.1.1.1 24
quit
interface vlan 200
ip address 192.168.1.1 24
quit

//// B
system-view
vlan batch 100 400
//interface ethernet 0/0/1
//port hybrid pvid vlan 100
//port hybrid untagged vlan 100

interface vlan 100
ip address 10.1.1.2 24
quit
interface vlan 400
ip address 192.168.2.1 24
quit

//// C
system-view
vlan batch 200 400 300
interface vlan 200
ip address 192.168.1.2 24
quit
interface vlan 400
ip address 192.168.2.2 24
quit
interface vlan 300
ip address 20.1.1.1 24
quit

//// A
// use ospf routing protocol to do this
system-view
ospf 1
area 0
network 10.1.1.0 0.0.0.255
network 192.168.1.0 0.0.0.255
quit
quit

//// B
system-view
ospf 1
area 0
network 10.1.1.0 0.0.0.255
network 192.168.2.0 0.0.0.255
quit
quit

//// C
system-view
ospf 1
area 0
network 192.168.1.0 0.0.0.255
network 192.168.2.0 0.0.0.255
network 20.1.1.0 0.0.0.255
quit
quit

//// set VRRP
// A
interface vlan 100
vrrp vrid 1 virtual-ip 10.1.1.111
vrrp vrid 1 priority 120
vrrp vrid 2 virtual-ip 10.1.1.112
vrrp vrid 2 priority 100
quit

// B
interface vlan 100
vrrp vrid 1 virtual-ip 10.1.1.111
vrrp vrid 1 priority 100
vrrp vrid 2 virtual-ip 10.1.1.112
vrrp vrid 2 priority 120
quit

---------------

静态路由的配置