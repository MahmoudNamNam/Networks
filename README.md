# Fundamentals of Networking

## Client-server architecture 
architecture of a computer network in which many clients (remote processors) request and receive service from a centralized server (host computer). Client computers provide an interface to allow a computer user to request services of the server and to display the results the server returns. Here are the key components and characteristics of client-server architecture:

1. **Client:** The client is the end-user device or application that requests services or resources from the server. Clients can be desktop computers, laptops, mobile devices, or even other servers. Clients initiate communication with the server to request data, processing, or other services.

2. **Server:** The server is a powerful computer or software application that provides specific services or resources to clients. Servers are designed to handle multiple client requests concurrently and efficiently. Examples of servers include web servers, database servers, and file servers.

3. **Communication:** Clients and servers communicate with each other over a network using standard communication protocols such as TCP/IP (Transmission Control Protocol/Internet Protocol). The client initiates a request, and the server responds by providing the requested service or resource.

4. **Roles:** The client and server roles are well-defined. The client is responsible for initiating requests, while the server is responsible for processing these requests and providing the requested services. This clear separation of roles allows for specialization and scalability.

5. **Statelessness:** In many client-server interactions, the server treats each request from a client as an independent transaction, without retaining information about the client's state between requests. Statelessness simplifies server design and enhances scalability.

6. **Scalability:** Client-server architecture allows for scalability by distributing the load among multiple servers. As the number of clients increases, additional servers can be added to handle the increased demand. This makes it easier to scale the system horizontally.

7. **Security:** Security measures can be implemented at both the client and server sides. Access controls, encryption, and authentication mechanisms are commonly used to secure communications and data exchange between clients and servers.

8. **Examples:** Common examples of client-server architecture include web-based applications (where a web browser is the client and a web server provides web pages), database systems (where clients access a central database server), and email systems (where email clients communicate with email servers).

9. **Three-Tier Architecture:** In many cases, client-server architectures are implemented using a three-tier model, consisting of a presentation tier (client), an application tier (business logic), and a data tier (database server). This separation of concerns enhances modularity and maintainability.

Client-server architecture has been a fundamental model in the development of networked and distributed systems, allowing for efficient resource utilization, centralization of data and services, and easier maintenance and management of systems.


---


## OSI Model

### 7. Application Layer

The application layer is used by end-user software such as web browsers and email clients. It provides protocols that allow software to send and receive information and present meaningful data to users. A few examples of application layer protocols are the Hypertext Transfer Protocol (HTTP), File Transfer Protocol (FTP), Post Office Protocol (POP), Simple Mail Transfer Protocol (SMTP), and Domain Name System (DNS).

### 6. Presentation Layer

The presentation layer prepares data for the application layer. It defines how two devices should encode, encrypt, and compress data so it is received correctly on the other end. The presentation layer takes any data transmitted by the application layer and prepares it for transmission over the session layer.

### 5. Session Layer

The session layer creates communication channels, called sessions, between devices. It is responsible for opening sessions, ensuring they remain open and functional while data is being transferred, and closing them when communication ends. The session layer can also set checkpoints during a data transfer—if the session is interrupted, devices can resume data transfer from the last checkpoint.

### 4. Transport Layer

The transport layer takes data transferred in the session layer and breaks it into “segments” on the transmitting end. It is responsible for reassembling the segments on the receiving end, turning it back into data that can be used by the session layer. The transport layer carries out flow control, sending data at a rate that matches the connection speed of the receiving device, and error control, checking if data was received incorrectly and if not, requesting it again.

### 3. Network Layer

The network layer has two main functions. One is breaking up segments into network packets, and reassembling the packets on the receiving end. The other is routing packets by discovering the best path across a physical network. The network layer uses network addresses (typically Internet Protocol addresses) to route packets to a destination node.

### 2. Data Link Layer

The data link layer establishes and terminates a connection between two physically-connected nodes on a network. It breaks up packets into frames and sends them from source to destination. This layer is composed of two parts—Logical Link Control (LLC), which identifies network protocols, performs error checking and synchronizes frames, and Media Access Control (MAC) which uses MAC addresses to connect devices and define permissions to transmit and receive data.

### 1. Physical Layer

The physical layer is responsible for the physical cable or wireless connection between network nodes. It defines the connector, the electrical cable or wireless technology connecting the devices, and is responsible for transmission of the raw data, which is simply a series of 0s and 1s, while taking care of bit rate control.

