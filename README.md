# Data-Comm-Routing

### Problem Statement
The objective is to assess the performance of the distance-vector routing protocol as well as the spanning tree routing protocol within a simulated network environment. The evaluation will focus on factors such as convergence time, scalability, resource utilization, and adaptability to network changes. The objective was achieved through the use of multiple simulated routers, switches, and end devices to form a complex topology, which included various subnets and allowed for the simulation of diverse network scenarios, such as redundant paths, network failures, and port security.

### Getting Started

Download Cisco Packet Tracer by following these links:

IF you are experienced to Cisco Packet Tracer, Use SkillsforAll via 

  https://skillsforall.com/resources/lab-downloads
  
If you are new to Cisco Packet Tracer, you still have to enroll in a Free course over at netacademy via 

  https://www.netacad.com/virtual/app/introduction-packet-tracer

### File Description

#### 5RouterBFS.pkt:
This file was developed to only use RIP for choosing between two routes  when transmitting a message between the two end devices. It is a small scale network made up of 5 routers and 2 PCs. It was used to learn how to set up a network within Cisco Packet Tracer and test the RIP commands listed above.

#### BellmanFordSim.pkt:
This file was the most simple network designed that used STP and RIP. It was made to learn how to set up a network within Cisco Packet Tracer as well as get a better understanding of how packets are transmitted.

#### Combined_STP_RSTP.pkt:
This file was developed to check how the RSTP, STP and RIP behave with each other when implemented in the same network using Cisco Packet Tracer. Small network was used to check the compatibility of protocols.


#### Complex_RSTP.pkt:
This file was developed to see behavior of RSTP when implemented in a large network and see the difference in the convergence time. Port guard was also implemented in this network.


#### Complex_STP.pkt:
This file was developed to see behavior of STP when implemented in a medium network and see the difference in the convergence time. 

#### Routing_Demo.pkt:
This file was developed to demonstrate the final network routing with RIP and STP.. The network presented in the Routing_Demo.pkt shows implementation of multiple routing protocols like Spanning-Tree Protocol, Rapid Spanning-Tree Protocol and Routing Information Protocol.

### Information

The network presented in the Routing_Demo.pkt shows implementation of multiple routing protocols like Spanning-Tree Protocol, Rapid Spanning-Tree Protocol and Routing Information Protocol.

STP and RSTP: 

- Configuration bridge protocol data units (BPDUs) and other information will be sent by this selected root bridge to its directly linked switches, who will then transmit the BPDUs to their surrounding switches. Every switch has a bridge ID priority value (BID), which is made up of the switch's MAC address and priority value (which is 32768 by default). The root bridge will be the switch with the lowest BID.
  
- The following steps will be taken in this process until a root port is chosen:
1. A switch port recognizes another switch as the root bridge when it gets superior BPDUs from that switch.
2. If it is feasible, the port with the lowest root path is chosen as the root port.
3. The switch will designate the port with the lowest sender BID as the root port if the path cost is equal.
4. The port on the sending switch with the lowest physical port number will be chosen as the root bridge (as the last tiebreaker) if the sender BID is the same, which is typically the same switch.

### Bellman Ford

The Routing Information Protocol (RIP) is an interior gateway protocol (IGP) that was developed to be used in small, homogeneous networks. RIP is a distance vector routing protocol, like Bellman-Ford, that utilizes broadcast User Datagram Protocol (UDP) packets to exchange routing information. Routing information updates are sent every 30 seconds from the router. If a router doesn’t receive an update from another router for 180 seconds or more then the routes that use that router are marked as unusable. After 240 seconds if there is still no update then the routes marked as unusable will be removed from the routing table. RIP uses hop counts as the metric for rating different routes. The hop count is the number of routers that are passed through in a given route. If the hop count of a route is greater than 15 then the route is determined to be unreachable, which is why RIP is less suitable for large networks. RIP routing also has to be configured within each of the routers by entering all of the IP addresses of the ports used on the router to allow packets to be transmitted through them.

### Spanning Tree

1. Below commands were used to configure Switches implementing STP and RSTP using the CLI terminal:

    1. Command to enable STP:

            en

            config t

            spanning-tree mode pvst

    2. Command to enable RSTP:
    
            en

            config t

            spanning-tree mode rapid-pvst

    3. Command to configure BPDUguard for securing end devices against any misconfigurations or intentional attempts to introduce new switches:
    
            en

            config t

            int fa 0/1 [switch port number connected to end device]

            spanning-tree bpduguard enable

    4. Command to shut and enable port of a switch:
    
            en

            config t

            int fa 0/1 [switch port number]

            shut

            no shut


     5. Command to ping end devices (run on PC/end device command terminal):
     
            ping -t [destination IP address]

      6. Command to change root bridge if there are multiple root bridges or we manually need to change root bridge:
      
              en

              config t

              spanning-tree vlan 1 root primary

2. Below commands used for Routers implementing RIP using the CLI terminal:

    1. Command to find hops in Router:
   
            en
       
            traceroute [destination IP address]


    2. Command to ping end devices (run on PC/end device command terminal):
       
            ping -t [destination IP address]


    4. Command to determine administrative distance (used by routers to determine which protocol to use for routing):
       
            en
       
            show ip route

### Lesson Learned

- Even what appeared to be the simplest software has somewhat of a learning curve.
- CPT is mostly for simple network verification and learning. 
- There were limitations with Cisco Packet Tracer in terms of finding applicable metrics
- Some limitations from simulating our design with Cisco Packet Tracer are that we don't account for environmental factors that can affect wireless communication and all of our simulations are 2-dimensional


### Video Link
https://youtu.be/MCOwCoYdBCs 

### References
https://youtu.be/En9nqOF_2rY?si=i2865QSubR9CDVvI

https://youtu.be/e1cD2KIme-E?si=_zd5gxkyi68u1fSQ

https://youtu.be/8W5lNKC8Y_8?si=zYmtH0QSedp7AFwL

https://youtu.be/0P8jGtIIz7k?si=mUKkFml9vZfO0cuv

https://youtu.be/MUgnX8ywZIY?si=Nz4o1xRFJjsK64E-

https://youtu.be/-KeRZB3HPQM?si=8sIw4iTPSMytgZ8B

https://youtu.be/3Tot1DjBD58?si=6hCoX0as0l1XTAnd

https://youtu.be/PBiGjxHSmRI?si=ZiXReeVGqHsp-5Sc

https://youtu.be/PBiGjxHSmRI?si=2yI_E7FqAoILAdHM

https://youtu.be/D7mAEs6m_UA?si=7UK8oXCf8rYM2lcH

https://www.cisco.com/c/en/us/td/docs/switches/lan/catalyst9300/software/release/16-12/configuration_guide/rtng/b_1612_rtng_9300_cg/configuring_rip.pdf

https://www.cisco.com/c/en/us/support/docs/ip/border-gateway-protocol-bgp/15986-admin-distance.html

https://iopscience.iop.org/article/10.1088/1742-6596/1007/1/012009/pdf
