# Explaining Network Topologies
## Networking Overview
### Networking Concepts
- **Network**: Two or more computer systems linked by a transmission medium and share one or more protocols that enable them to exchange data
- Networks are thought of in 2 terms:
  - Nodes
    - Devices that send, receive, and forward data
    - Two types of nodes:
      - Intermediate
        - Perform a forwarding function
      - End systems (Hosts)
        - Send and receive data traffic
  - Links
    - Communications pathways between nodes
#### Client-Server vs. Peer-to-Per Networks
- End system nodes are classified as the following:
  - Server
    - Makes network apps and resources available to other hosts
  - Client
    - Comsumes the services provided by servers
- **Client-server network**:
  - Nodes such as PCs, laptops, and smartphones act as clients
  - Servers are more powerful comuters
  - Application services and resources are centrally provisioned, managed, and secured
  - Business and Enterprise networks fall under this category
  - Most often, hosts will function as both clients & servers.
- **Peer-to-Peer network**:
  - Each host acts ad a client and server.
  - Decentralized model where provision, management, and security of services & data are distributed.
  - Small network can be reffered to as a workgroup
  - Residential networks fall under this category
#### Appliances, Applications, and Functions
- Networks have all three
- **Appliances**
  - Networks make use of many types of specialized platforms.
  - An appliance is a computer with an OS and software designed to perform a speicific network role.
  - Examples include Switches, Routers, WAPs (Wireless Access Points) that forward data, firewalls/IDS that enforce security rules, and load balancers and proxies for improving network performance.
  - These can be deployed as physical hardware, meaning the OS has its own CPU, memory, storage, and Network Interfaces.
  - Possible to deploy virtual appliances, meaning OS is deployed as a VM running on a hypervisor
    - This hypervisor can run multiple different virtual appliances
- **Applications**
  - Nodes and links of networking infrastructure are deployed to run services
  - Services are shared apps that allow network to do useful work (sharing files or allowing for email)
- **Functions**
  - Networks can be configured with additional properties to perform different functions
  - Example 1: Security properties of a VPN allow devices to join a local network from across the internet.
  - Example 2: QoS functionality allows optimization of a network to suit a time-sensitive app such as voice/video
## Network Types
- Network types refers to its size & scope
  - Size of a network is measured by the number of nodes
  - Scope refers to the area the nodes sharing the same network address are ditributed
### Local Area Networks (LAN)
- Confined to a single Geographical location.
- All nodes and segments are directly connected with cables/short-range less Tech.
- Most of the infrastructure is directly owned & managed by a single organization
- Examples of LANS:
  - Home/residential
    - With Internet router and a few computers, mobile devices, gaming consols and printers
  - Small office/home office (SOHO)
    - Business-oriented network possible ysing a centralized server in addition to client devices and printers
    - Still uses a single Router/switch/Access point for connectivity
  - Small and medium-sized enterprise (SME)
    - Network supporting dozens of users
    - Utilizes structured cabling and multiple switches and routers to provide connectivity
  - Enterprise LAN
    - Larger network with hundreds-thousands of servers and clients.
    - Require multiple enterprise-class swithc & router appliances to maintain performace levels.
  - Datacenter
    - Hosts only servers & storage, not end user client devices.
### Wide Are Networks (WAN)
- Network of networks, connected by long-distance links.
- Typial Enterprise WAN connects a main office site with multple branch offices, possibly in different countries
- Can link 2+ large LANs or used for remote workers connecting to an enterprise network via public networks.
- WAN links are also used to connect datacenters together
- Likely to use leased network devices and links, operated and managed by a service provider.
## Network Topology
- Topology describes the physical/logical structure of the netowkr in terms of nodes and links
- Physical topology
  - Describes the placement of nodes and how they are connected by trasmission media
  - Example:
    - Net 1: Modes are directly connected via a single cable.
    - Net 2: Each node connects to a switching appliance via seperate cables
- Logical topology
  - Describes the flow of data through the network
  - Example:
    - If in each case the nodes can send messages to one another, their topology is the same
    - Different physical implementations achieve the same logical layout (directly connected vs connected to same switch)
- Point-to-Point (PtP) link
  - Single link is established between two nodes
  - Because only 2 devices share the connection, they are guaranteed a level of bandwidth
- Physical PtP topology
  - See below for different media types for half-duplex and duplex comms:
    <img width="768" height="438" alt="image" src="https://github.com/user-attachments/assets/4d311b7a-b777-4852-9224-4c84414178c8" />

- PtP can be physical or logical topology.
- Example:
  - On a WAN, 2 router appliances might be physically linked via multple intermediate netowkrs and physical devices but still share a logical PtP, where each can only address the oother router.
- With either topology, it is the 1:1 relationship that defines a PtP link.

## Star Toplogy
- Each endpoint node is connected to a central forwarding appliance (Switch/Router)
- The central node communicates between the endpoints
- This is the most widely used physical topology
- Example:
  - A typical SOHO network is based around a single Router that clients can connect to via a cable or wirelessly.
- This topology is easy to reconfigure and troubleshoot due to all the data going through a central point.
- This point can be used to monitor and manage the network.
- Faults are automatically isolated to the media, node, switch, router or WAP at the center of the star
- See below different concentrators for Star topologies:
  <img width="768" height="424" alt="image" src="https://github.com/user-attachments/assets/79b29e2c-9a36-4038-8855-1195267be5e7" />

- You can also encounter **hub-and spoke** topologies:
  - Looks identical to a Star but is used in differnt context
  - These are more commonly applied to WANs with remote sites vs LANs for Start topology.

## Mesh Topology
- Commonly used in WANs, especially public networks
- Full mesh networks require each device to have a PtP link with every other device on the network
  - This approach is normally impractical
  - Number of links rquired is expressed as `n(n-1)2/` where n=nodes
  - Example:
    - A network with 4 nodes would requre 6 links, while a network with 40 nodes would need 780 links.
- A hybrid approach is often used, with only the most important devices interconnected in the mesh.
  - Can include extra links for fault tolerance and redundancy.
  - This is reffered to as a partial mesh.
- See below the difference between a fully connected and partial mesh topology:
  <img width="768" height="412" alt="image" src="https://github.com/user-attachments/assets/a4a94399-1136-4f9e-a0d4-061a3189b403" />

- Mesh networks provide excellent rudundancy due to routes via intermediary devices being available between locations if a link failure occurs.

## Legacy Topologies
- Most networks use the Star Topology due to its reliability and scalability
- The following topologies are no longer in widespread use, but can still be found in legacy systems.
### Bus Topology
<img width="133" height="75" alt="image" src="https://github.com/user-attachments/assets/77b14cd8-deaf-4ba3-a1b7-ed57bdbff77a" />

- Consists of a trunk cable with nodes inserted directly into the trunk or tapped into the trunk using offshoot (drop) cables.
- Device called _Terminator_ is placed at both ends
  - Purpose is to absorb signals, preventing them from reflecting back and forth
- Signals travel from one node to all other nodes
- Major downside is that 1 broken cable anywhere breaks the termination and prevents communication between all devices.
  - This makes it difficult to isolate cabling problems
### Ring Topology
<img width="126" height="112" alt="image" src="https://github.com/user-attachments/assets/74f46a07-c1eb-4952-8030-dbfaaad71188" />

- Connects neighboring nodes until they form a ring/circle.
- Signals travel in one direction around the ring, with each device acting as a repeater.
- The installation requires careful planning
- A node malfunction/cable break can prevent signals from reaching nodes beyond the malfunction.
- This can cause difficulties with problem isolation, requiring troubleshooter to check several physical locations

# OSI Model Concepts
## Open Systems Interconnection Model (OSI Model)




























