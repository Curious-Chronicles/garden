---
index: SS16
marks: 5
tags: entrance, network-and-telecommunication
related: [[]]
status: Completed
created: [[2023-05-06]]
---

## 1. Network topologies (bus, star, ring, mesh)

Network topologies refer to the physical or logical layout or structure of a computer network. They define how devices are connected to each other and how data flows within the network. Here are the key network topologies and their definitions:

1. Bus Topology:
- Definition: In a bus topology, all devices are connected to a common communication medium, known as a bus. The devices share this single communication channel to transmit and receive data.
- Example: A simple example of a bus topology is an Ethernet network where all devices are connected to a central cable.

2. Star Topology:
- Definition: In a star topology, all devices are connected to a central device, such as a switch or hub. The central device acts as a central point of communication and controls the flow of data between devices.
- Example: A local area network (LAN) using a central switch to connect multiple computers is an example of a star topology.

3. Ring Topology:
- Definition: In a ring topology, devices are connected in a closed loop, forming a ring. Each device in the network is connected to exactly two other devices, creating a continuous circular pathway for data transmission.
- Example: Token Ring networks, although less common today, used a ring topology where devices were connected in a closed loop and passed a special token to control access to the network.

4. Mesh Topology:
- Definition: In a mesh topology, each device is connected to every other device in the network. It provides redundant paths for data transmission, improving fault tolerance and reliability.
- Example: Large-scale networks, such as the Internet, utilize a mesh topology where multiple routers are interconnected to create multiple paths for data to travel between devices.

## 2. Network protocols (TCP/IP, HTTP, FTP, SMTP, POP3, IMAP)

Network protocols are sets of rules and conventions that govern the communication between devices on a computer network. They define how data is formatted, transmitted, received, and interpreted. Here are some commonly used network protocols and their definitions:

1. TCP/IP (Transmission Control Protocol/Internet Protocol):
- Definition: TCP/IP is the foundational protocol suite used for communication on the internet. It provides a reliable and connection-oriented transmission of data between devices over an IP network.
- Example: When you browse the web, TCP/IP is used to establish a connection with a web server and transmit the web pages to your browser.

2. HTTP (Hypertext Transfer Protocol):
- Definition: HTTP is a protocol used for transmitting hypertext, such as HTML files, over the internet. It enables communication between web browsers and web servers.
- Example: When you enter a URL in your browser's address bar and load a web page, HTTP is responsible for requesting and delivering the webpage's content.

3. FTP (File Transfer Protocol):
- Definition: FTP is a protocol used for transferring files between computers on a network. It provides a way to upload and download files from a remote server.
- Example: FTP is commonly used by web developers to upload website files to a web server or to download files from a remote server.

4. SMTP (Simple Mail Transfer Protocol):
- Definition: SMTP is a protocol used for sending email messages between servers. It defines how email clients communicate with mail servers to send and relay messages.
- Example: When you send an email from your email client, SMTP is responsible for routing the email to the appropriate mail server for delivery.

5. POP3 (Post Office Protocol version 3):
- Definition: POP3 is a protocol used by email clients to retrieve email messages from a mail server. It allows users to download and store emails locally on their devices.
- Example: When you use an email client to check your inbox and download new messages, POP3 is used to retrieve those messages from the mail server.

6. IMAP (Internet Message Access Protocol):
- Definition: IMAP is a protocol used for accessing email stored on a remote mail server. It allows users to manage their email messages without downloading them to their devices.
- Example: IMAP is commonly used by users who want to access their emails from multiple devices and keep their messages synchronized across different platforms.

## 3. OSI reference model

The OSI (Open Systems Interconnection) reference model is a conceptual framework that standardizes the functions of a communication system into seven layers. Each layer performs specific tasks, and together they enable communication between devices on a network. Here are the seven layers of the OSI reference model:

1. Physical Layer:
- Definition: The physical layer is responsible for transmitting raw bitstream data over the physical medium, such as cables or wireless signals. It deals with electrical, mechanical, and physical aspects of data transmission.
- Example: Ethernet cables, fiber optic cables, and wireless signals are all part of the physical layer.

2. Data Link Layer:
- Definition: The data link layer ensures reliable transmission of data over a physical link by providing error detection and correction. It organizes data into frames and manages access to the physical medium.
- Example: Ethernet and Wi-Fi protocols operate at the data link layer.

3. Network Layer:
- Definition: The network layer handles the routing of data packets from the source to the destination across different networks. It determines the best path for data transmission and handles logical addressing.
- Example: The Internet Protocol (IP) is a network layer protocol used for addressing and routing data packets on the internet.

4. Transport Layer:
- Definition: The transport layer provides end-to-end data delivery and ensures reliable, error-free transmission. It breaks large data chunks into smaller segments, manages flow control, and performs error recovery.
- Example: Transmission Control Protocol (TCP) is a transport layer protocol that guarantees reliable data delivery by establishing connections and managing acknowledgments.

5. Session Layer:
- Definition: The session layer establishes, manages, and terminates sessions between applications. It handles session synchronization, checkpointing, and recovery.
- Example: Session control protocols, such as the Remote Procedure Call (RPC), operate at the session layer.

6. Presentation Layer:
- Definition: The presentation layer deals with data representation and ensures that information exchanged between systems is in a compatible format. It handles encryption, compression, and data conversion.
- Example: The Secure Sockets Layer (SSL) protocol, used for secure communication over the web, operates at the presentation layer.

7. Application Layer:
- Definition: The application layer provides services directly to the end-user applications. It enables user interaction and supports specific application-level protocols.
- Example: HTTP (Hypertext Transfer Protocol) and SMTP (Simple Mail Transfer Protocol) are application layer protocols used for web browsing and email communication, respectively.

The OSI reference model helps in understanding and organizing the different layers involved in network communication. It provides a common framework for designing, implementing, and troubleshooting network protocols and systems.

## 4. Network devices (router, switch, hub, modem, firewall)

1. Router:
- Definition: A router is a network device that forwards data packets between different networks based on their IP addresses. It determines the optimal path for data transmission and helps connect multiple networks together.
- Example: Cisco ISR (Integrated Services Router) series.

2. Switch:
- Definition: A switch is a network device that connects multiple devices within a local area network (LAN). It forwards data packets based on MAC addresses and creates a dedicated communication path between devices.
- Example: Cisco Catalyst series switches.

3. Hub:
- Definition: A hub is a basic network device that connects multiple devices in a network, but it does not perform any packet filtering or address-based forwarding. It simply broadcasts incoming data to all connected devices.
- Example: Passive Ethernet hub.

4. Modem:
- Definition: A modem (modulator-demodulator) is a device that converts digital signals from a computer into analog signals that can be transmitted over telephone or cable lines. It also converts analog signals back into digital form at the receiving end.
- Example: Cable modem, DSL modem.

5. Firewall:
- Definition: A firewall is a network security device that monitors and filters network traffic based on predetermined security rules. It acts as a barrier between internal and external networks, protecting against unauthorized access and potential threats.
- Example: Cisco ASA (Adaptive Security Appliance) firewall.

These network devices play crucial roles in establishing and managing network connections, ensuring efficient data transmission, and enhancing network security. Each device serves a specific purpose and contributes to the overall functionality and performance of a network.

## 5. Network addressing (IP addresses, MAC addresses)

1. IP Address:
- Definition: An IP (Internet Protocol) address is a numerical label assigned to each device connected to a computer network. It provides a unique identifier for devices to communicate and locate each other on an IP-based network.
- Example: 192.168.0.1

2. MAC Address:
- Definition: A MAC (Media Access Control) address is a unique identifier assigned to the network interface of a device. It is a hardware address that is embedded in the network adapter and used for communication at the data link layer of the network protocol stack.
- Example: 00:1A:2B:3C:4D:5E

IP addresses are used for routing and logical addressing, while MAC addresses are used for identifying devices within a local network. IP addresses are hierarchical and can be assigned dynamically or statically, whereas MAC addresses are assigned by the manufacturer and typically remain fixed for the lifetime of a device.

IP addresses are essential for internet communication, while MAC addresses are primarily used for local network communication.

## 6. Network security (firewalls, encryption, authentication, authorization)

1. Firewalls:
- Definition: A firewall is a network security device that monitors and controls incoming and outgoing network traffic based on predetermined security rules. It acts as a barrier between internal and external networks, preventing unauthorized access and protecting against network threats.
- Example: A firewall can be configured to block incoming connections from specific IP addresses or restrict certain types of network traffic.

2. Encryption:
- Definition: Encryption is the process of converting data into a secure and unreadable format to prevent unauthorized access during transmission or storage. It ensures that only authorized parties can access and understand the data by using encryption algorithms and keys.
- Example: Secure Socket Layer (SSL) and Transport Layer Security (TLS) are commonly used encryption protocols for securing data transmitted over the internet.

3. Authentication:
- Definition: Authentication is the process of verifying the identity of a user or device attempting to access a network or system. It involves presenting credentials such as usernames, passwords, or digital certificates to prove authenticity.
- Example: A user entering a username and password to log in to a network or a device using a fingerprint scanner for authentication.

4. Authorization:
- Definition: Authorization is the process of granting or denying access rights and permissions to authenticated users or devices based on their roles, privileges, or other criteria. It ensures that users have appropriate access levels and can only perform authorized actions.
- Example: An employee being granted read-only access to certain files on a network drive while managers have read and write access.

These network security measures work together to protect data, networks, and systems from unauthorized access, data breaches, and malicious activities. Firewalls control network traffic, encryption secures data, authentication verifies identities, and authorization ensures appropriate access levels.

## 7. Network types (LAN, WAN, MAN)

1. LAN (Local Area Network):
- Definition: A LAN is a network that connects devices within a limited geographic area, such as a home, office building, or campus. It is typically owned and managed by a single organization and facilitates communication and resource sharing among connected devices.
- Example: An office network where computers, printers, and servers are interconnected to share files, access shared resources, and communicate with each other.

2. WAN (Wide Area Network):
- Definition: A WAN is a network that spans a large geographical area, connecting multiple LANs or other networks together. It allows for long-distance communication and is often used to connect branch offices, data centers, or even networks across different countries.
- Example: An organization with branch offices located in different cities that are connected via dedicated leased lines or virtual private networks (VPNs) to enable centralized data access and collaboration.

3. MAN (Metropolitan Area Network):
- Definition: A MAN is a network that spans a larger area than a LAN but smaller than a WAN, typically covering a city or metropolitan area. It provides high-speed connectivity to connect various LANs or other networks within the same region.
- Example: A city-wide network connecting multiple government offices, educational institutions, and businesses to share resources, access shared databases, and enable efficient communication.

These network types differ in terms of their geographic coverage and the scale of connectivity they provide. LANs are localized networks within a limited area, WANs connect geographically dispersed networks, and MANs cover larger metropolitan areas, serving as an intermediate between LANs and WANs.

## 8. Wireless networks (Wi-Fi, Bluetooth, cellular networks)

1. Wi-Fi (Wireless Fidelity):
- Definition: Wi-Fi is a wireless networking technology that allows devices to connect to a local area network (LAN) without the need for physical wired connections. It uses radio waves to transmit data between devices and provides internet access and network connectivity in homes, offices, and public places.
- Example: Connecting a laptop, smartphone, or tablet to a wireless router at home or a Wi-Fi hotspot in a coffee shop to access the internet and communicate with other devices on the network.

2. Bluetooth:
- Definition: Bluetooth is a short-range wireless communication technology used for connecting devices in close proximity. It enables the transfer of data and audio between devices, such as smartphones, tablets, laptops, and peripherals like headphones, speakers, and keyboards.
- Example: Pairing a smartphone with wireless earbuds to listen to music or connecting a laptop with a Bluetooth-enabled mouse for wireless cursor control.

3. Cellular Networks:
- Definition: Cellular networks, also known as mobile networks, provide wireless communication over long distances using a network of base stations. They allow mobile devices such as smartphones and tablets to connect to the internet and make voice calls through cellular service providers.
- Example: Making phone calls, sending text messages, and accessing the internet on a smartphone using 4G or 5G cellular networks.

These wireless technologies offer different capabilities and applications. Wi-Fi provides local wireless connectivity within a limited area, Bluetooth enables short-range device-to-device communication, and cellular networks provide wide-area wireless connectivity for mobile devices.

## 9. Network performance metrics (bandwidth, latency, throughput)

1. Bandwidth:
- Definition: Bandwidth refers to the maximum amount of data that can be transmitted over a network within a given time frame. It represents the capacity of the network to transfer data and is typically measured in bits per second (bps).
- Example: A network with a bandwidth of 100 Mbps can transfer up to 100 million bits of data per second.

2. Latency:
- Definition: Latency is the amount of time it takes for data to travel from the source to the destination in a network. It is often measured as the round-trip time (RTT) and is usually expressed in milliseconds (ms).
- Example: If the latency of a network connection is 50 ms, it means that it takes 50 milliseconds for a packet of data to travel from the source to the destination and back.

3. Throughput:
- Definition: Throughput is the actual amount of data that is successfully transmitted over a network within a given time period. It represents the effective data transfer rate and is measured in bits per second (bps).
- Example: If a network has a throughput of 1 Gbps, it means that it can transfer up to 1 billion bits of data per second.

These network performance metrics are crucial for assessing and optimizing the efficiency and effectiveness of network communication. Bandwidth determines the maximum data transfer capacity, latency measures the delay in data transmission, and throughput represents the actual data transfer rate achieved in practice.

## 10. Network troubleshooting techniques (ping, traceroute, netstat)

1. Ping:
- Definition: Ping is a network utility used to test the reachability of a host or a network device. It sends an ICMP echo request message to the target host and waits for an ICMP echo reply message to determine if the host is reachable and measure the round-trip time.
- Example: In command prompt or terminal, typing "ping www.example.com" will send ICMP echo requests to the specified website and display the round-trip time and packet loss information.

2. Traceroute:
- Definition: Traceroute is a network diagnostic tool used to trace the path that packets take from the source host to a destination host. It sends a series of ICMP or UDP packets with incrementally increasing TTL values to discover the network routers along the path.
- Example: Running the command "traceroute www.example.com" will display the list of routers and their IP addresses that the packets traverse from your local network to the destination host.

3. Netstat:
- Definition: Netstat is a command-line tool used to display network statistics and active network connections on a host. It provides information about open ports, active connections, routing tables, and other network-related information.
- Example: Executing the command "netstat -a" will show all active connections and listening ports on the local machine, along with the corresponding IP addresses and port numbers.

These network troubleshooting techniques are valuable for diagnosing network connectivity issues and identifying potential problems along the network path. Ping helps determine if a host is reachable, traceroute reveals the path taken by packets, and netstat provides insights into active network connections and ports.

