# Network Security Fundamentals
Understanding of the OSI model as it will be used to map tools and also protocols
Helps one to understand how a network works, securing and investigation of network logs during invetigating of audits

# Tracks 
OSI/TCP-IP Model , Subnetting , Routing 

# Basics- Network Devices
Host | IP Address | Network | Repeater |Hub | Bridge | Switch | Router |

# Host
 - Any device connected to the network which sends or recieves data(Server,Phone,IP Phone,Internet of Things ).
 - Host are categorised into client and server where special software are programmed to execute specific commands such as sending or recieving data.
 - A website will request data from a web server(This makes the website in the browser a client and the (webserver) a server.In the same way a webserver relies on a file server to update the webpages hence making the web server a client and the (file server) a server.
 
# IP ADDRESS
- This is the logical identity of a host in the network
- Made of 32 bit binary each divided into 4 octates(each octate contains 8 bits).
-                    192   .  168   .    1   .  236
-                  11000000.10101000.00000001.11101100
-
# Network 
- Transports traffic between hosts.Created when two computers are connected and carrying out communication.
     - Logical Grouping of hosts which require similar connectivity.
     - Networks can contain other networks.
     - Sub-Networks(Subnet).
-Internet-Network of networks

# Repeater
- Responsible for regeneration of signal allowing communication over greater distances.

# Hub
- Multi Port Repeater.Allowing host to be connected centrally and have communication between each other.
- Facilitates scaling communication between multiple hosts.

# Bridges
- Sits between hub connected hosts.
- Bridges only have two ports.
- Bridges learn which hosts are on which side (Help Contain Packets onlyto there relative networks).

# Switches 
- Facilitates communication within a network.
- Switches are a combinations of a hub and repeater.
  - Multiple Ports.
  - Learns which hosts are on each port (Ensuring that communication occurs onthe relative ports).
  -All hosts in the network share the same ip address space.

# Routers
- Facilitates communication between networks.
- Provides a traffic control point where security policies, filtering, redirecting can be handled.
  - Routers learn which networks they are attached to.
    - Known as routes - Stored in a routing table.
    - Routing table - all networks a router knows about.

- Have IP Addresses in the networks they are attached to.
  - This IP addresses are GATEWAYS providing each host way out of their local network.
  - Create the Hierarchy in networks and the entire internet.

# -(Routers facilitate communication between networks while switches facilitate communication within the network)-
