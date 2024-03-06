![image](https://github.com/MahmoudNamNam/Networks/assets/148398760/de6846f0-20c0-4fc5-bf58-b33b87747bc2)


# **Chapter 2 Network Architecture**

### **Network Architecture Overview: Four-Layer TCP/IP Model**

To design and construct a complex system like the Internet, engineers adopt an approach of breaking down the overarching problem into smaller, manageable subproblems. The architects of the initial internets identified **four** fundamental areas of engineering, each addressing a specific aspect of the network. These areas are named and organized into layers, forming the foundation of the Internet architecture:

![image](https://github.com/MahmoudNamNam/Networks/assets/148398760/4170c548-8728-49cb-9cc8-64d1867b8c8a)


1. **Link Layer:**
   - **Function:** Connects the computer to the local network, managing data transmission over wired or wireless connections.
   - **Responsibility:** Handling the physical network media, such as cables or radio signals.
   - **Example:** Wired Ethernet, WiFi, cellular networks.

2. **Internetwork Layer:**
   - **Function:** Determines the best route for data packets from the source to the destination across multiple networks.
   - **Responsibility:** Addresses routing and forwarding of packets, connecting different networks.
   - **Example:** Internet Protocol (IP) is used to implement this layer.

3. **Transport Layer:**
   - **Function:** Ensures reliable data transfer between devices, managing end-to-end communication.
   - **Responsibility:** Handling segmentation, reassembly, error detection, and flow control.
   - **Example:** Transport Control Protocol (TCP) is employed for reliable communication.

4. **Application Layer:**
   - **Function:** Facilitates networked applications and user interactions.
   - **Responsibility:** Encompasses various applications that end-users engage with, such as web browsers and email clients.
   - **Example:** Web browsers, file transfer applications.

**TCP/IP Model Visualization:**
   - The layers are represented as a stack, with the Link layer at the bottom and the Application layer at the top.
   - Visualized as a model with four layers, known informally as the "TCP/IP model."

**Protocol Implementation:**
   - The model is informally referred to as the "TCP/IP model" due to the implementation of Transport Control Protocol (TCP) for the Transport layer and Internet Protocol (IP) for the Internetwork layer.

**Layered Approach:**
   - The layered structure simplifies the engineering process, allowing different groups to independently work on specific layers before integrating them to solve the overarching problem.

In the subsequent sections, each layer will be examined in more detail, starting from the bottom layer (Link layer).


### **2.1 Link Layer Overview:**
1. **Responsibility:**
   - Connects the computer to the local network and facilitates data movement across a single hop.

2. **Common Technologies:**
   - Wireless networking is the predominant technology.
   - Wireless devices communicate within limited distances, and switching between towers may occur during movement.
   - Wired connections (e.g., Ethernet cables) are also common, with cables typically under 100 meters.

3. **Shared Networks:**
   - Link layer technologies are often shared among multiple computers in the same location.

### **Challenges and Solutions:**
1. **Encoding and Sending Data:**
   - For wireless connections, agreement on radio frequencies and data encoding.
   - For wired connections, agreement on voltage and transmission speed.
   - For fiber optics, agreement on light frequencies and transmission speed.

2. **Cooperation Among Computers:**
   - Agreement on how to cooperate when multiple computers want to send data simultaneously.
   - Collision avoidance is crucial to prevent chaos and noise on the network.

### **Carrier Sense Multiple Access with Collision Detection (CSMA/CD):**
1. **Objective:**
   - Enable fair sharing of the network among multiple computers.

2. **Process:**
   - Before sending data, a computer listens (carrier sense) to check if the network is clear.
   - If the network is clear, the computer starts sending its data.
   - The computer listens while sending to detect collisions.
   - In the event of a collision, both computers stop, wait, and retry transmission after different waiting periods.
3. **After Transmission:**
   - After sending a packet, a computer pauses to allow other waiting computers a chance to send data.
   - If another computer senses the pause and starts sending, the original computer waits until the transmission is complete before attempting to send again.

    ![image](https://github.com/MahmoudNamNam/Networks/assets/148398760/bd9eeff2-900a-4477-b3cc-b6e9f7500c7c)
    



### **Shared and Non-Shared Link Layers:**
1. **Shared Connections:**
   - Technologies like cellular, WiFi, satellite, and cable modems use CSMA/CD for fair access.
   - Multiple computers share the same network connection.

2. **Non-Shared Connections:**
   - Fiber optic cables and leased lines are generally not shared.
   - Typically not shared among multiple users simultaneously.

### **Transmission Across Multiple Links (Hops):**
   - To move data over long distances, it passes through multiple routers connected by various link layers.
   - Each transition from one router to another is referred to as a "hop."

### **Conclusion:**
   - Link layer technologies focus on enabling the transmission of data across a single link, ranging from short distances to hundreds of kilometers.
   - For longer distances, data passes through multiple routers, and each transition between routers is considered a hop.



-----------
### **2.2 Internetwork Layer (IP) Overview:**

1. **Role of Routers:**
   - The Internetwork Layer, represented by IP (Internet Protocol), comes into play once a packet reaches a router.
   - Routers determine the best route for the packet based on its destination address.

2. **Routing Approach:**
   - Given the vast number of destination computers, routers don't have detailed information about every possible destination.
   - Routers make educated guesses on how to move the packet closer to its destination.

3. **Progressive Knowledge:**
   - As the packet progresses through routers, each router has a better understanding of the packet's destination.

### **Analogy to Traveling:**

1. **Holiday Trip Analogy:**
   - Compares the routing of packets to planning a holiday trip with multiple transportation modes (hops).

2. **Example Journey:**
   - Describes how, during travel, information about the exact destination becomes clearer as one gets closer.

3. **Analogy to Internet Routing:**
   - Similar to routers in the Internet, where only routers closest to the destination have precise information about the path.

![image](https://github.com/MahmoudNamNam/Networks/assets/148398760/6b5bb49b-06e9-430f-bfa9-c7100abed24f)


### **Adaptability to Changes:**

1. **Handling Unexpected Issues:**
   - Acknowledges that unexpected issues or delays may occur during packet transmission, requiring a change in plans.

2. **Router Adaptation:**
   - Routers exchange messages to inform each other of traffic delays or network outages.
   - Core routers in the Internet are intelligent and quickly adapt to outages or failures, rerouting packets as needed.

3. **Reasons for Network Issues:**
   - Network slowdowns due to overload, physical damage (e.g., cut wires), or natural disasters like hurricanes.

### **Packet Loss and the Next Layer:**

1. **Dealing with Lost Packets:**
   - Acknowledges that sometimes packets are lost during transmission.
   - Teases that the next layer in the architecture addresses the issue of dealing with lost packets.

### **Conclusion:**

The Internet Protocol (IP) is an essential component of the Internetwork Layer and is responsible for directing packets across the Internet. IP follows a sequential method to guide packets based on their destination addresses. This process can be compared to planning a vacation trip, where the routers progressively move closer to the final destination. The layer also emphasizes the adaptability of routers to unexpected problems and introduces the concept of handling lost packets in the following layer of the architecture.

-----

### **2.3 Transport Layer (TCP) Overview:**

1. **Purpose:**
   - The Transport Layer, represented by TCP (Transmission Control Protocol), deals with the reliable delivery of packets over the Internet.

2. **Handling Packet Issues:**
   - Acknowledges that packets may get lost, delayed, or arrive out of order during transmission.

3. **Packet Contents:**
   - Each packet contains the source and destination computer's addresses and an offset indicating its position relative to the beginning of the message.

4. **Reconstruction at Destination:**
   - The destination computer reconstructs the original message using packet offsets and lengths, even if received out of order.

### **Acknowledgment and Resending:**

1. **Acknowledgment Process:**
   - The destination periodically sends acknowledgments to the source indicating how much of the message it has received and reconstructed.

2. **Detecting Missing Parts:**
   - If parts of the reconstructed message are missing, indicating lost or badly delayed packets, the destination requests the source to resend the missing data.

### **Flow Control:**

1. **Data Storage at Source:**
   - The source computer stores sent message parts until acknowledgment of successful receipt is received from the destination.

2. **Window Size:**
   - The amount of data sent before waiting for acknowledgment is called the "window size."
  
3. **Optimizing Window Size:**
   - To avoid slowing down transmission or overloading the network, the window size is adjusted.
   - Initially kept small, and adjusted based on the speed of acknowledgments.

### **Adapting to Network Conditions:**

1. **Network Load Consideration:**
   - Window size adjustment based on network conditions prevents overloading routers or communication lines.

2. **Courtesy on the Internet:**
   - Similar to Link layer, practicing courtesy on the Internet helps ensure efficient use of shared network infrastructure.

### **Network Speed Adaptation:**

1. **High-Speed Connections:**
   - In high-speed and lightly loaded networks, data is sent quickly.
  
2. **Slow or Heavily Loaded Connections:**
   - In slow or heavily loaded networks, data transmission is slowed down to match connection limitations.

### **Conclusion:**

TCP, operating at the Transport Layer, ensures reliable packet delivery by addressing issues such as packet loss, delay, and out-of-order arrival. The acknowledgment process, window size adjustment, and consideration of network conditions contribute to the efficient and adaptive transmission of data over the Internet. Practicing courtesy in data transmission helps maintain the integrity of the shared network infrastructure.

----

### **2.4 Application Layer Overview:**

1. **Collaboration of Layers:**
   - The Link, Internetwork, and Transport layers collaborate to efficiently move data across shared networks.

2. **Purpose of Application Layer:**
   - Focuses on the development and use of networked applications that utilize reliable data connections.

### **Evolution of Networked Applications:**

1. **Early Internet Applications (1980s):**
   - Logging into remote computers, file transfers, email, and real-time text chats were among the first widely used networked applications.

2. **Emergence of World Wide Web (1990s):**
   - With improved computer capabilities, the World Wide Web (WWW) application became prominent.
   - Originally focused on reading and editing networked hypertext documents with images.

3. **Dominance of Web Application:**
   - Today, the web is the most common and widely used network application globally.
   - Older Internet applications like remote logins, file transfers, and email continue to be in use.

### **Client-Server Architecture:**

1. **Application Components:**
   - Each application is typically divided into two halves: the "server" and the "client."

2. **Server and Client Roles:**
   - The server runs on the destination computer, waiting for incoming network connections.
   - The client runs on the source computer, making connections to servers and displaying content.

3. **Web Browsing Example:**
   - Web browsers (e.g., Firefox, Chrome, Internet Explorer) function as web clients, making connections to web servers and displaying content.
   - URLs in the browser's address bar represent the web servers contacted by the client to retrieve documents.

### **Application Protocol Definition:**

1. **Necessity of Application Protocols:**
   - Developing a networked application involves defining an "application protocol."
   - Describes how the server and client halves of the application exchange messages over the network.

2. **Specialized Protocols:**
   - Application layer protocols are specialized to meet the unique needs of each application.

### **Future Exploration:**

1. **Upcoming Exploration:**
   - Future exploration will delve into specific Application layer protocols.

### **Conclusion:**

The Application Layer is responsible for developing and utilizing networked applications that take advantage of the effective data transfer facilitated by the lower layers. As time has passed, the kinds of applications have changed, with the web becoming the most widespread. The client-server architecture is a prevalent model, with particular application protocols designed to satisfy the unique needs of each application.
