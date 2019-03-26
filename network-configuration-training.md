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
//Let's assume another switch have a ip address 1.1.1.6
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