# Data-Comm-Routing

### Problem Statement
The objective is to assess the performance of the distance-vector routing protocol as well as the spanning tree routing protocol within a simulated network environment. The evaluation will focus on factors such as convergence time, scalability, resource utilization, and adaptability to network changes. The objective was achieved through the use of multiple simulated routers, switches, and end devices to form a complex topology, which included various subnets and allowed for the simulation of diverse network scenarios, such as redundant paths, network failures, and port security.

### Bellman Ford

### Spanning Tree

The network presented in the Routing_Demo.pkt shows implementation of multiple routing protocols like Spanning-Tree Protocol, Rapid Spanning-Tree Protocol and Routing Information Protocol.

STP and RSTP: 

- Configuration bridge protocol data units (BPDUs) and other information will be sent by this selected root bridge to its directly linked switches, who will then transmit the BPDUs to their surrounding switches. Every switch has a bridge ID priority value (BID), which is made up of the switch's MAC address and priority value (which is 32768 by default). The root bridge will be the switch with the lowest BID.
  
- The following steps will be taken in this process until a root port is chosen:
1. A switch port recognizes another switch as the root bridge when it gets superior BPDUs from that switch.
2. If it is feasible, the port with the lowest root path is chosen as the root port.
3. The switch will designate the port with the lowest sender BID as the root port if the path cost is equal.
4. The port on the sending switch with the lowest physical port number will be chosen as the root bridge (as the last tiebreaker) if the sender BID is the same, which is typically the same switch.


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


     5. Command to ping end devices:
     
            ping -t [destination IP address]

      6. Command to change root bridge if there are multiple root bridges or we manually need to change root bridge:
      
              en

              config t

              spanning-tree vlan 1 root primary

2. Below commands used for Routers implementing RIP using the CLI terminal:

    1. Command to find hops in Router:
   
            en
       
            traceroute [destination IP address]


    2. Command to ping end devices:
       
            ping -t [destination IP address]


    4. Command to determine administrative distance (used by routers to determine which protocol to use for routing):
       
            en
       
            show ip route


### Video Link
https://youtu.be/MCOwCoYdBCs 

### Reference
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


