# Network Protocols

Network protocols are divided into three main categories: communication protocols, management protocols, and security protocols. It's important to know the protocols listed below for an entry-level security analyst role.

## Communication Protocols

Communication protocols govern the exchange of information in network transmission. They dictate how data is transmitted between devices, the timing of communication, and methods to recover data lost in transit.

### Transmission Control Protocol (TCP)

*   **Function:** Allows two devices to form a connection and stream data.
*   **Process:** Uses a three-way handshake:
    1.  Device sends a synchronize (SYN) request to a server.
    2.  Server responds with a SYN/ACK packet to acknowledge receipt of the device’s request.
    3.  Server receives the final ACK packet from the device, establishing a TCP connection.
*   **Layer (TCP/IP Model):** Transport Layer

### User Datagram Protocol (UDP)

*   **Function:** A connectionless protocol that doesn’t establish a connection before transmission.
*   **Reliability:** Less reliable than TCP.
*   **Speed:** Faster than TCP.
*   **Use Case:** Sending DNS requests to local DNS servers.
*   **Layer (TCP/IP Model):** Transport Layer

### Hypertext Transfer Protocol (HTTP)

*   **Function:** Provides a method of communication between clients and website servers.
*   **Port:** 80
*   **Security:** Insecure; being replaced on most websites by HTTPS.
*   **Layer (TCP/IP Model):** Application Layer

### Domain Name System (DNS)

*   **Function:** Translates internet domain names into IP addresses.
*   **Process:** A client computer sends a query to a dedicated DNS server. The DNS server looks up the IP address that corresponds to the website domain.
*   **Protocol:** Normally uses UDP on port 53. Switches to TCP if the DNS reply is large.
*   **Layer (TCP/IP Model):** Application Layer

## Management Protocols

Management protocols are used for monitoring and managing activity on a network. They include protocols for error reporting and optimizing performance on the network.

### Simple Network Management Protocol (SNMP)

*   **Function:** Used for monitoring and managing devices on a network.
*   **Capabilities:** Can reset a password on a network device, change its baseline configuration, or send requests to network devices for a report on network bandwidth usage.
*   **Layer (TCP/IP Model):** Application Layer

### Internet Control Message Protocol (ICMP)

*   **Function:** Used by devices to communicate data transmission errors across the network.
*   **Use Case:** Used to troubleshoot network connectivity and latency by issuing the “ping” command.
*   **Layer (TCP/IP Model):** Internet Layer

### Dynamic Host Configuration Protocol (DHCP)

*   **Function:** Configures devices on a network.
*   **Process:** Works with the router to assign a unique IP address to each device and provide the addresses of the appropriate DNS server and default gateway.
*   **Ports:** DHCP servers operate on UDP port 67; DHCP clients operate on UDP port 68.

## Security Protocols

Security protocols ensure that data is sent and received securely across a network. They use encryption algorithms to protect data in transit.

### Hypertext Transfer Protocol Secure (HTTPS)

*   **Function:** Provides a secure method of communication between clients and website servers.
*   **Security:** Uses secure sockets layer/transport layer security (SSL/TLS) encryption on all transmissions.
*   **Port:** 443
*   **Layer (TCP/IP Model):** Application Layer

### Secure File Transfer Protocol (SFTP)

*   **Function:** Securely transfers files from one device to another over a network.
*   **Technology:** Uses secure shell (SSH), typically through TCP port 22. SSH uses Advanced Encryption Standard (AES) and other types of encryption.
*   **Use Case:** Used often with cloud storage (uploading or downloading files).
*   **Layer (TCP/IP Model):** Application Layer

**Note:** The encryption protocols mentioned do not conceal the source or destination IP address of network traffic.

### Network Address Translation (NAT)

*   **Function:** Allows devices with private IP addresses to communicate with the public internet using a single public IP address.
*   **Process:** For outgoing messages, the router replaces a private source IP address with its public IP address and performs the reverse operation for responses.
*   **Requirement:** Requires a router or firewall specifically configured to perform NAT.
*   **Layer (TCP/IP Model):** NAT is a part of layer 3 (internet layer) and layer 4 (transport layer) of the TCP/IP model.

### Address Resolution Protocol (ARP)

*   **Function:** Translates the IP addresses found in data packets into the MAC address of the hardware device.
*   **Process:** Each device on the network performs ARP and keeps track of matching IP and MAC addresses in an ARP cache.
*   **Layer (TCP/IP Model):** Network Access Layer
*   **Note:** ARP does not have a specific port number since it is a layer 2 protocol and port numbers are associated with the layer 7 application layer.

### Telnet

*   **Function:** Used to connect with a remote system.
*   **Security:** Sends all information in clear text; not as secure as SSH.
*   **Port:** Uses TCP port 23.
*   **Layer (TCP/IP Model):** Application Layer

### Secure Shell (SSH)

*   **Function:** Creates a secure connection with a remote system.
*   **Security:** Provides secure authentication and encrypted communication.
*   **Port:** Operates over TCP port 22.
*   **Use Case:** A replacement for less secure protocols, such as Telnet.
*   **Layer (TCP/IP Model):** Application Layer

### Post Office Protocol (POP)

*   **Function:** Used to manage and retrieve email from a mail server.
*   **Version:** POP3 is the most commonly used version.
*   **Process:** User devices send requests to the remote mail server and download email messages locally.
*   **Ports:**
    *   Unencrypted, plaintext authentication: TCP/UDP port 110
    *   Encrypted emails (SSL/TLS): TCP/UDP port 995
*   **Layer (TCP/IP Model):** Application Layer
*   **Limitations:** Mail has to finish downloading on a local device before it can be read. After downloading, the mail may or may not be deleted from the mail server, so it does not guarantee that a user can sync the same email across multiple devices.

### Internet Message Access Protocol (IMAP)

*   **Function:** Used for incoming email.
*   **Process:** Downloads the headers of emails and the message content. The content also remains on the email server, which allows users to access their email from multiple devices.
*   **Ports:**
    *   Unencrypted: TCP port 143
    *   Encrypted (TLS): TCP port 993
*   **Layer (TCP/IP Model):** Application Layer
*   **Advantages:** Allows users to partially read email before it is finished downloading. Since the mail is kept on the mail server, it allows a user to sync emails across multiple devices.

### Simple Mail Transfer Protocol (SMTP)

*   **Function:** Used to transmit and route email from the sender to the recipient’s address.
*   **Process:** Works with Message Transfer Agent (MTA) software, which searches DNS servers to resolve email addresses to IP addresses.
*   **Ports:**
    *   Unencrypted: TCP/UDP port 25
    *   Encrypted (TLS): TCP/UDP port 587
*   **Layer (TCP/IP Model):** Application Layer
*   **Note:** The TCP port 25 is often used by high-volume spam. SMTP helps to filter out spam by regulating how many emails a source can send at a time.

### Protocols and Port Numbers

Port numbers are used by network devices to determine what should be done with the information contained in each data packet once they reach their destination. Firewalls can filter out unwanted traffic based on port numbers. For example, an organization may configure a firewall to only allow access to TCP port 995 (POP3) by IP addresses belonging to the organization.
