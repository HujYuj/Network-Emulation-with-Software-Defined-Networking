## 1
$ofctl add-flow s0 \
    in_port=1,ip,nw_src=10.0.0.2,nw_dst=10.0.1.2,actions=mod_dl_src:0A:00:0A:01:00:02,mod_dl_dst:0A:00:0A:FE:00:02,output=2 

- add-flow s0: add openflow rules to s0
- in_port=1 : for the packets coming from port 1
- ip : for the packets using ip protocol
- nw_src=10.0.0.2 : for the packets with source ip address = 10.0.0.2
- actions: the actions going to take
- mod_dl_src:0A:00:0A:01:00:02 : modify the packet's source MAC to : 0A:00:0A:01:00:02
- mod_dl_dst:0A:00:0A:FE:00:02 : modify the packet's destination MAC to 0A:00:0A:FE:00:02
- output=2 : forward the pack to output port 2

## 2
$ofctl add-flow s0 \
    in_port=2,ip,nw_src=10.0.1.2,nw_dst=10.0.0.2,actions=mod_dl_src:0A:00:00:01:00:01,mod_dl_dst:0A:00:00:02:00:00,output=1 

- add-flow s0: add openflow rules to s0
- in_port=2 : for the packets coming from port 2
- ip : for the packets using ip protocol
- nw_src=10.0.1.2 : for the packets with source ip address = 10.0.1.2
- actions: the actions going to take
- mod_dl_src:0A:00:00:01:00:01 : modify the packet's source MAC to : 0A:00:00:01:00:01
- mod_dl_dst:0A:00:00:02:00:00 : modify the packet's destination MAC to 0A:00:00:02:00:00
- output=1 : forward the pack to output port 1

## 3
$ofctl add-flow s1 \
    in_port=2,ip,nw_src=10.0.0.2,nw_dst=10.0.1.2,actions=mod_dl_src:0A:00:01:01:00:01,mod_dl_dst:0A:00:01:02:00:00,output=1 

- add-flow s1: add openflow rules to s1
- in_port=2 : for the packets coming from port 2
- ip : for the packets using ip protocol
- nw_src=10.0.0.2 : for the packets with source ip address = 10.0.0.2
- actions: the actions going to take
- mod_dl_src:0A:00:01:01:00:01 : modify the packet's source MAC to : 0A:00:01:01:00:01
- mod_dl_dst:0A:00:01:02:00:00 : modify the packet's destination MAC to 0A:00:01:02:00:00
- output=1 : forward the pack to output port 1

## 4
$ofctl add-flow s1 \
    in_port=1,ip,nw_src=10.0.1.2,nw_dst=10.0.0.2,actions=mod_dl_src:0A:00:0A:FE:00:02,mod_dl_dst:0A:00:0A:01:00:02,output=2 

- add-flow s1: add openflow rules to s1
- in_port=1 : for the packets coming from port 1
- ip : for the packets using ip protocol
- nw_src=10.0.1.2 : for the packets with source ip address = 10.0.1.2
- actions: the actions going to take
- mod_dl_src:0A:00:0A:FE:00:02 : modify the packet's source MAC to : 0A:00:0A:FE:00:02
- mod_dl_dst:0A:00:0A:01:00:02 : modify the packet's destination MAC to 0A:00:0A:01:00:02
- output=2 : forward the pack to output port 2
