---
index: SE12
marks: 30
tags: entrance, it-fundatmentals
related: [[]]
status: Todo
created: [[2023-05-06]]
---

## 1. Introduction to computer hardware and software

Computer hardware - It refers to the physical parts or components of a computer. It encompasses of the tangible parts (_that takes physical space_). Some of the component computer hardware has are: 
1. **Central Processing Unit (CPU)**: Its the brain and core of the computer system. It helps in operation if calculation and execution commands.
2. **Memory (RAM)**: RAM stands for Random Access Memory, and further divided into S-RAM(_Static RAM_) or D-RAM(_Dynamic RAM_). It helps in storing temporary information that computer might required. 
3. **Storage Device**: It is used for storing information for longer period of time. There are various types of Storage device such as: SSD, and HHD. 
4. **Input and Output Devices**: Devices that are connected to the computer system that helps either in the Input into the system or provide Output to the user. Some of the essential input/output devices are: 
	1. Input - Keyboard, Mouse, and Scanner. 
	2. Output - Monitor, and Printer
5. **Network and Internet**: They are devices and component in the computer system that helps in the access of information across other computer system. It helps in communication and connection between each other. Some of the components are: Router, Hub, Switch and Modem. 

Computer Software: It refers to the program, application, and instruction that tells computer what to do. It consists of intangible (_a.k.a it does not have physical and are digital_). Some examples are:
1. **Operating System (OS)**: It is the core of software that manages the computer resources and provide an interface for users to interact with the computer.
2. **Application**: They are software programs that make use of the resources of physical component to perform a set of command or tasks. 

## 2. Basic computer organization and architecture

**Computer Architecture**

**Computer Organization**
The way hardware components are arranged and interconnected. It focuses on the internal structure and design of a computer. 

1. **Central Processing Unit (CPU):** The CPU is the main component of a computer that performs most of the processing. It executes instructions, performs calculations, and manages data.
2. **Memory Hierarchy**: The memory hierarchy consists of different levels of memory, including registers, cache, main memory (RAM), and secondary storage (hard drives or solid-state drives). These levels vary in terms of capacity, speed, and cost, with registers being the fastest but smallest, and secondary storage being slower but offering more storage capacity.
3. **Instruction Set Architecture (ISA**): The ISA defines the set of instructions that a CPU can execute. It includes the instructions, data types, addressing modes, and registers available to programmers.
4. **Bus System**: Buses are the communication channels through which data and control signals travel between different components of a computer system. They include the address bus, data bus, and control bus.

**Computer Architecture**:
Computer architecture refers to the design and organization of a computer system, encompassing both hardware and software aspects. It involves how the hardware components work together to execute instructions and process data. Here are a couple of key terms related to computer architecture:
1. **Von Neumann Architecture**: The Von Neumann architecture is a fundamental computer architecture design that separates memory and processing. It includes a CPU, memory, input/output devices, and a bus system. Instructions and data are stored in the same memory, and the CPU fetches and executes instructions sequentially.
2. **Pipelining**: Pipelining is a technique used in CPUs to improve instruction execution efficiency. It divides the instruction execution process into stages, allowing multiple instructions to be processed simultaneously at different stages of the pipeline.
3. **Caches**: Caches are small, fast memory units located closer to the CPU. They store frequently accessed data and instructions, reducing the time needed to access them from slower main memory.

**Additional Sub-Topics:**

**Parallel Processing:**
Parallel processing involves using multiple processors or cores to perform computations simultaneously, thereby increasing overall processing speed and efficiency.

**Instruction Level Parallelism (ILP):**
ILP refers to techniques and technologies that allow instructions within a program to be executed in parallel, exploiting dependencies and overlapping execution to improve performance.

**Memory Management:**
Memory management involves allocating and managing memory resources in a computer system. It includes techniques such as virtual memory, which allows programs to use more memory than is physically available.

**Input/Output Systems**:
Input/output systems deal with how computers interact with peripheral devices, such as keyboards, mice, displays, and storage devices. It includes protocols, interfaces, and techniques for efficient data transfer between the computer and external devices.

## 3. Computer networks and communication technologies

1. Network Topologies:
- Bus Topology: All devices are connected to a common backbone or communication line.
- Star Topology: All devices are connected to a central hub or switch.
- Ring Topology: Devices are connected in a circular manner, forming a ring.
- Mesh Topology: Each device is connected to every other device in the network.

2. Network Protocols:
- TCP/IP (Transmission Control Protocol/Internet Protocol): The standard protocol suite used for communication over the Internet.
- HTTP (Hypertext Transfer Protocol): Used for transferring hypertext documents on the World Wide Web.
- FTP (File Transfer Protocol): Used for transferring files between a client and a server.
- SMTP (Simple Mail Transfer Protocol): Used for sending email messages between servers.

3. Network Devices:
- Router: Connects multiple networks and forwards data packets between them.
- Switch: Connects devices within a network and forwards data packets to the intended recipient.
- Modem: Converts digital signals from a computer to analog signals for transmission over a communication line.
- Network Interface Card (NIC): Enables a device to connect to a network and communicate with other devices.

4. Network Security:
- Firewall: Acts as a barrier between a private network and external networks, filtering incoming and outgoing traffic.
- Encryption: Converts data into a secure format to prevent unauthorized access.
- Authentication: Verifies the identity of users or devices before granting access to the network.
- Intrusion Detection System (IDS): Monitors network traffic for potential security breaches.

Example MCQs:
1. Which network topology connects all devices to a central hub or switch?
   a) Bus topology
   b) Star topology
   c) Ring topology
   d) Mesh topology
   (Correct Answer: b) Star topology)

2. Which protocol is used for transferring files between a client and a server?
   a) TCP/IP
   b) HTTP
   c) FTP
   d) SMTP
   (Correct Answer: c) FTP)

3. Which network device connects multiple networks and forwards data packets between them?
   a) Router
   b) Switch
   c) Modem
   d) NIC
   (Correct Answer: a) Router)

4. What is the purpose of a firewall in a network?
   a) Transfers files between a client and a server
   b) Connects multiple networks and forwards data packets
   c) Converts digital signals to analog signals
   d) Acts as a barrier and filters network traffic
   (Correct Answer: d) Acts as a barrier and filters network traffic)

5. Which security mechanism converts data into a secure format to prevent unauthorized access?
   a) Firewall
   b) Encryption
   c) Authentication
   d) IDS
   (Correct Answer: b) Encryption)

## 4. Operating systems and their functionalities

1. Process Management:
- Process Scheduling: Determines the order in which processes are executed by the CPU.
- Process Synchronization: Ensures that multiple processes share resources in a coordinated manner.
- Process Communication: Facilitates the exchange of data and information between processes.

2. Memory Management:
- Memory Allocation: Assigns memory blocks to processes based on their memory requirements.
- Memory Paging: Divides the physical memory into fixed-size pages and maps them to logical addresses.
- Virtual Memory: Allows processes to access more memory than physically available by using disk space as an extension.

3. File Systems:
- File Organization: Specifies how files are stored and organized on storage devices.
- File Access Methods: Define how files are accessed and retrieved by processes.
- File Permissions: Control the level of access and permissions granted to users for files and directories.

4. Device Management:
- Device Drivers: Provide an interface between the operating system and hardware devices.
- I/O Scheduling: Determines the order in which I/O requests from processes are serviced.
- Device Allocation: Manages the allocation of devices to processes and resolves conflicts.

5. User Interface:
- Command-Line Interface (CLI): Users interact with the operating system by entering text commands.
- Graphical User Interface (GUI): Users interact with the operating system through visual elements such as icons and windows.
- Shell: A command interpreter that allows users to interact with the operating system through a CLI.

Example MCQs:
1. Which component of an operating system is responsible for allocating memory to processes?
   a) Process scheduling
   b) Memory paging
   c) File organization
   d) Device drivers
   (Correct Answer: b) Memory paging)

2. What is the role of a device driver in an operating system?
   a) Allocating memory to processes
   b) Scheduling processes
   c) Managing I/O devices
   d) Providing a user interface
   (Correct Answer: c) Managing I/O devices)

3. Which user interface allows users to interact with the operating system through visual elements?
   a) Command-Line Interface (CLI)
   b) Graphical User Interface (GUI)
   c) Shell
   d) Device driver
   (Correct Answer: b) Graphical User Interface (GUI))

4. Which file system component controls the level of access and permissions granted to users for files?
   a) File organization
   b) File access methods
   c) File permissions
   d) Virtual memory
   (Correct Answer: c) File permissions)

5. What does process synchronization ensure in an operating system?
   a) Efficient memory allocation
   b) Coordinated sharing of resources
   c) Fast process scheduling
   d) Secure file access
   (Correct Answer: b) Coordinated sharing of resources)

## 5. Fundamentals of programming and algorithms

1. Programming Paradigms:
- Procedural Programming: Organizes the program as a sequence of procedures or functions.
- Object-Oriented Programming (OOP): Structures the program around objects that encapsulate data and behavior.
- Functional Programming: Emphasizes the use of pure functions and avoids mutable state and side effects.

2. Data Types and Variables:
- Primitive Data Types: Basic data types provided by the programming language (e.g., integers, floating-point numbers, booleans).
- Composite Data Types: Data structures that combine multiple values (e.g., arrays, lists, dictionaries).
- Variables: Named memory locations used to store and manipulate data.

3. Control Structures:
- Conditional Statements: Allow the program to make decisions based on certain conditions (e.g., if-else statements, switch statements).
- Loops: Repeat a certain block of code until a specific condition is met (e.g., for loops, while loops).

4. Functions and Procedures:
- Functions: Named blocks of code that can be called and executed with a set of input arguments, and return a value.
- Procedures: Similar to functions but do not return a value.

5. Algorithms and Problem Solving:
- Algorithm: A step-by-step procedure or set of instructions for solving a problem.
- Algorithm Design Techniques: Approaches for developing efficient algorithms (e.g., divide and conquer, greedy algorithms, dynamic programming).
- Problem Solving: The process of formulating problems, analyzing them, and finding solutions.

Example MCQs:
1. Which programming paradigm focuses on organizing the program around objects?
   a) Procedural programming
   b) Object-oriented programming (OOP)
   c) Functional programming
   d) None of the above
   (Correct Answer: b) Object-oriented programming (OOP))

2. Which data type represents a whole number in programming?
   a) String
   b) Boolean
   c) Integer
   d) Float
   (Correct Answer: c) Integer)

3. What is the purpose of a loop in programming?
   a) To store and manipulate data
   b) To make decisions based on conditions
   c) To repeat a block of code until a condition is met
   d) To define the behavior of an object
   (Correct Answer: c) To repeat a block of code until a condition is met)

4. What is the role of an algorithm in programming?
   a) To organize code into functions and procedures
   b) To define the data types used in a program
   c) To solve a problem by providing a step-by-step procedure
   d) To store and manipulate data in memory
   (Correct Answer: c) To solve a problem by providing a step-by-step procedure)

5. Which algorithm design technique involves breaking down a problem into smaller subproblems and solving them recursively?
   a) Divide and conquer
   b) Greedy algorithms
   c) Dynamic programming
   d) Backtracking
   (Correct Answer: a) Divide and conquer)


## 6. Database management systems and their basic concepts

1. Database:
- Definition: A structured collection of data stored electronically and organized in a way that allows efficient retrieval, manipulation, and management.
- Example: An online shopping website's database containing product information, customer details, and order history.

2. Relational Database Management System (RDBMS):
- Definition: A type of database management system that organizes data into tables with relationships defined between them.
- Example: MySQL, Oracle, Microsoft SQL Server.

3. Data Models:
- Definition: Representations of the structure of a database, including the types of data, relationships, and constraints.
- Example: Relational data model, hierarchical data model, network data model.

4. Entities, Attributes, and Relationships:
- Entity: Represents a distinct object or concept in the real world, such as a person, place, or event.
- Attribute: Descriptive characteristics or properties of an entity.
- Relationship: Association between entities, indicating how they are related.
- Example: In a university database, "Student" is an entity with attributes like name, student ID, and age. The relationship "Enroll" connects students with courses.

5. Structured Query Language (SQL):
- Definition: A programming language used to communicate with and manage relational databases.
- Example: SQL commands like SELECT, INSERT, UPDATE, and DELETE are used to retrieve, insert, update, and delete data from a database.

Example MCQs:
1. Which term refers to a structured collection of data stored electronically?
   a) Database
   b) Data model
   c) RDBMS
   d) SQL
   (Correct Answer: a) Database)

2. Which type of database management system organizes data into tables with defined relationships?
   a) Relational database management system (RDBMS)
   b) Hierarchical database management system
   c) Network database management system
   d) NoSQL database management system
   (Correct Answer: a) Relational database management system (RDBMS))

3. What is an attribute in a database?
   a) An association between entities
   b) A distinct object or concept in the real world
   c) A descriptive characteristic or property of an entity
   d) A representation of the structure of a database
   (Correct Answer: c) A descriptive characteristic or property of an entity)

4. Which data model represents data as a collection of tables with relationships defined between them?
   a) Relational data model
   b) Hierarchical data model
   c) Network data model
   d) NoSQL data model
   (Correct Answer: a) Relational data model)

5. Which programming language is commonly used to manage relational databases?
   a) HTML
   b) JavaScript
   c) SQL
   d) Python
   (Correct Answer: c) SQL)


## 7. Web technologies and their applications

1. Hypertext Markup Language (HTML):
- Definition: The standard markup language used for creating the structure and content of web pages.
- Example: Using HTML tags to define headings, paragraphs, lists, links, images, and other elements on a web page.

2. Cascading Style Sheets (CSS):
- Definition: A style sheet language used for describing the presentation and layout of web pages.
- Example: Applying CSS rules to control the font styles, colors, spacing, and positioning of HTML elements on a web page.

3. JavaScript:
- Definition: A programming language that enables interactive and dynamic behavior on web pages.
- Example: Writing JavaScript code to validate form inputs, create animations, handle user interactions, and fetch data from servers.

4. Web Servers:
- Definition: Software applications that handle client requests and deliver web pages and resources over the internet.
- Example: Apache HTTP Server, Nginx, Microsoft IIS.

5. Client-Side Scripting vs. Server-Side Scripting:
- Client-Side Scripting: Executing scripts on the client's web browser to enhance user experience and perform tasks locally.
- Server-Side Scripting: Executing scripts on the web server to generate dynamic web pages and process data from clients.
- Example: JavaScript is a client-side scripting language, while PHP and Python are commonly used for server-side scripting.

6. Web Frameworks:
- Definition: Software frameworks that provide a structure and tools for developing web applications.
- Example: Ruby on Rails, Django, Angular, React.

Example MCQs:
1. Which technology is used to define the structure and content of web pages?
   a) HTML
   b) CSS
   c) JavaScript
   d) PHP
   (Correct Answer: a) HTML)

2. Which technology is used to control the presentation and layout of web pages?
   a) HTML
   b) CSS
   c) JavaScript
   d) Ruby
   (Correct Answer: b) CSS)

3. Which programming language enables interactivity on web pages?
   a) HTML
   b) CSS
   c) JavaScript
   d) Python
   (Correct Answer: c) JavaScript)

4. Which software is responsible for handling client requests and delivering web pages?
   a) Web server
   b) Web browser
   c) Web framework
   d) Web application
   (Correct Answer: a) Web server)

5. What is the main difference between client-side scripting and server-side scripting?
   a) Client-side scripting executes on the web server, while server-side scripting executes on the client's browser.
   b) Client-side scripting generates dynamic web pages, while server-side scripting enhances user experience.
   c) Client-side scripting runs on the client's browser, while server-side scripting runs on the web server.
   d) Client-side scripting requires a web framework, while server-side scripting does not.
   (Correct Answer: c) Client-side scripting runs on the client's browser, while server-side scripting runs on the web server)


## 8. Information security and cryptography

1. Information Security:
- Definition: The practice of protecting information from unauthorized access, use, disclosure, disruption, modification, or destruction.
- Sub-topics:
  a) Confidentiality: Ensuring that information is accessible only to authorized individuals.
  b) Integrity: Maintaining the accuracy and consistency of information.
  c) Availability: Ensuring that information is accessible and usable when needed.
  d) Authentication: Verifying the identity of individuals or entities.
  e) Authorization: Granting or restricting access to resources based on privileges.
  f) Non-repudiation: Preventing individuals from denying their actions or transactions.

2. Cryptography:
- Definition: The practice of securing communication by transforming information into an unreadable format using encryption algorithms.
- Sub-topics:
  a) Encryption: The process of converting plain text into ciphertext to protect its confidentiality.
  b) Decryption: The process of converting ciphertext back into plain text using a decryption key.
  c) Symmetric Encryption: Using the same key for both encryption and decryption.
  d) Asymmetric Encryption: Using different keys for encryption and decryption (public and private key pairs).
  e) Hash Functions: One-way mathematical functions used to generate fixed-size values (hashes) from input data.
  f) Digital Signatures: Using cryptographic techniques to provide authenticity and integrity of digital messages.

3. Threats and Attacks:
- Definition: Various types of threats and attacks that compromise information security.
- Sub-topics:
  a) Malware: Software designed to disrupt or damage computer systems.
  b) Phishing: Deceptive techniques to trick individuals into revealing sensitive information.
  c) Denial of Service (DoS): Overwhelming a system or network to make it unavailable to users.
  d) Man-in-the-Middle (MitM) Attack: Intercepting and altering communication between two parties.
  e) Social Engineering: Manipulating individuals to gain unauthorized access or information.
  f) Password Attacks: Techniques to obtain or guess passwords, such as brute-force or dictionary attacks.

Example MCQs:
1. Which term refers to the practice of protecting information from unauthorized access, use, disclosure, disruption, modification, or destruction?
   a) Encryption
   b) Cryptography
   c) Information security
   d) Authentication
   (Correct Answer: c) Information security)

2. What is the process of converting plain text into unreadable ciphertext to protect its confidentiality?
   a) Encryption
   b) Decryption
   c) Hashing
   d) Digital signature
   (Correct Answer: a) Encryption)

3. Which type of encryption uses different keys for encryption and decryption?
   a) Symmetric encryption
   b) Asymmetric encryption
   c) Hash encryption
   d) Digital signature encryption
   (Correct Answer: b) Asymmetric encryption)

4. What type of attack overwhelms a system or network to make it unavailable to users?
   a) Malware attack
   b) Phishing attack
   c) Denial of Service (DoS) attack
   d) Man-in-the-Middle (MitM) attack
   (Correct Answer: c) Denial of Service (DoS) attack)

5. Which term refers to manipulating individuals to gain unauthorized access or information?
   a) Malware
   b) Phishing
   c) Social engineering
   d) Password attack
   (Correct Answer: c) Social engineering)


## 9. Cloud computing and virtualization

1. Cloud Computing:
- Definition: The delivery of computing resources, including servers, storage, databases, software, and analytics, over the internet (the cloud).
- Sub-topics:
  a) Infrastructure as a Service (IaaS): Provides virtualized computing resources (servers, storage, networks) for users to build their own applications.
  b) Platform as a Service (PaaS): Offers a complete development and deployment environment, including operating systems, programming languages, and databases.
  c) Software as a Service (SaaS): Delivers ready-to-use software applications over the internet, accessible through web browsers or APIs.
  d) Public Cloud: Cloud services provided by third-party vendors and accessible to the public over the internet.
  e) Private Cloud: Cloud infrastructure solely dedicated to one organization, offering enhanced security and control.
  f) Hybrid Cloud: Combination of public and private cloud environments, allowing data and applications to be shared between them.

2. Virtualization:
- Definition: The creation of virtual versions of computing resources such as servers, storage, and networks.
- Sub-topics:
  a) Server Virtualization: Running multiple virtual servers on a single physical server, maximizing resource utilization.
  b) Desktop Virtualization: Providing virtual desktop environments to users, allowing remote access and central management.
  c) Network Virtualization: Creating virtual networks that are decoupled from physical network infrastructure, enabling flexibility and scalability.
  d) Hypervisor: Software that enables the creation and management of virtual machines on physical hardware.
  e) Virtual Machine (VM): An emulation of a computer system, including the operating system, applications, and hardware components.

Example MCQs:
1. Which cloud computing service model provides virtualized computing resources for users to build their own applications?
   a) IaaS
   b) PaaS
   c) SaaS
   d) Public cloud
   (Correct Answer: a) IaaS)

2. What type of cloud infrastructure offers enhanced security and control, dedicated to a single organization?
   a) Public cloud
   b) Private cloud
   c) Hybrid cloud
   d) SaaS cloud
   (Correct Answer: b) Private cloud)

3. Which virtualization technique allows running multiple virtual servers on a single physical server?
   a) Server virtualization
   b) Desktop virtualization
   c) Network virtualization
   d) Hypervisor virtualization
   (Correct Answer: a) Server virtualization)

4. What is the purpose of a hypervisor in virtualization?
   a) Creation of virtual networks
   b) Central management of virtual desktops
   c) Emulation of a computer system
   d) Creation and management of virtual machines
   (Correct Answer: d) Creation and management of virtual machines)

5. Which cloud computing service model delivers ready-to-use software applications over the internet?
   a) IaaS
   b) PaaS
   c) SaaS
   d) Hybrid cloud
   (Correct Answer: c) SaaS)


## 10. Emerging trends and technologies in IT industry

1. Artificial Intelligence (AI):
- Definition: The development of computer systems capable of performing tasks that typically require human intelligence, such as speech recognition, decision-making, and problem-solving.
- Sub-topics:
  a) Machine Learning: AI algorithms that enable systems to learn and improve from data without explicit programming.
  b) Deep Learning: Subset of machine learning that focuses on neural networks with multiple layers to process complex patterns.
  c) Natural Language Processing (NLP): AI technology that enables computers to understand, interpret, and generate human language.
  d) Computer Vision: AI technology that allows computers to understand and interpret visual information from images or videos.

2. Internet of Things (IoT):
- Definition: The network of physical devices, vehicles, appliances, and other objects embedded with sensors, software, and connectivity to exchange data over the internet.
- Sub-topics:
  a) Sensors and Actuators: Devices that collect and transmit data from the physical environment and can perform actions based on received instructions.
  b) Connectivity: Technologies such as Wi-Fi, Bluetooth, and cellular networks that enable devices to communicate and share data.
  c) Data Analytics: Processing and analyzing the massive amount of data generated by IoT devices to extract meaningful insights.
  d) Smart Cities: IoT applications in urban environments to enhance efficiency, sustainability, and quality of life.

3. Blockchain Technology:
- Definition: A decentralized and distributed digital ledger that records transactions across multiple computers to ensure transparency, security, and immutability.
- Sub-topics:
  a) Cryptocurrency: Digital currencies like Bitcoin and Ethereum that rely on blockchain technology for secure and transparent transactions.
  b) Smart Contracts: Self-executing contracts with predefined rules and conditions encoded on the blockchain, eliminating the need for intermediaries.
  c) Supply Chain Management: Blockchain-based solutions for tracking and verifying the flow of goods and services across supply chains.
  d) Identity Management: Secure and tamper-proof storage of personal identity information using blockchain to combat identity theft and fraud.

Example MCQs:
1. Which subset of AI focuses on neural networks with multiple layers to process complex patterns?
   a) Machine Learning
   b) Deep Learning
   c) Natural Language Processing
   d) Computer Vision
   (Correct Answer: b) Deep Learning)

2. What technology enables devices to collect and transmit data over the internet?
   a) Machine Learning
   b) Artificial Intelligence
   c) Internet of Things
   d) Blockchain
   (Correct Answer: c) Internet of Things)

3. Which technology is a decentralized and distributed digital ledger that ensures transparency and security in transactions?
   a) Artificial Intelligence
   b) Internet of Things
   c) Blockchain
   d) Machine Learning
   (Correct Answer: c) Blockchain)

4. What is the term for self-executing contracts with predefined rules and conditions encoded on the blockchain?
   a) Deep Learning
   b) Smart Contracts
   c) Cryptocurrency
   d) Natural Language Processing
   (Correct Answer: b) Smart Contracts)

5. Which IoT application aims to enhance efficiency, sustainability, and quality of life in urban environments?
   a) Sensors and Actuators
   b) Connectivity
   c) Data Analytics
   d) Smart Cities
   (Correct Answer: d) Smart Cities)
