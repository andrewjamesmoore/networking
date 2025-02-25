# Network Protocols: A Comprehensive Overview

Network protocols can be divided into three main categories: communication protocols, management protocols, and security protocols. There are dozens of different network protocols, but you don’t need to memorize all of them for an entry-level security analyst role. However, it’s important for you to know the ones listed in this reading.

## Communication Protocols

Communication protocols govern the exchange of information in network transmission. They dictate how the data is transmitted between devices and the timing of the communication. They also include methods to recover data lost in transit. Here are a few of them.

### Transmission Control Protocol (TCP)

An internet communication protocol that allows two devices to form a connection and stream data. TCP uses a three-way handshake process.

**TCP Three-Way Handshake:**

1.  The device sends a synchronize (SYN) request to a server.
2.  The server responds with a SYN/ACK packet to acknowledge receipt of the device’s request.
3.  Once the server receives the final ACK packet from the device, a TCP connection is established.

- **Layer (TCP/IP Model):** Transport Layer

### User Datagram Protocol (UDP)

A connectionless protocol that does not establish a connection between devices before a transmission. This makes it less reliable than TCP. But it also means that it works well for transmissions that need to get to their destination quickly. For example, one use of UDP is for sending DNS requests to local DNS servers.

- **Layer (TCP/IP Model):** Transport Layer

### Hypertext Transfer Protocol (HTTP)

An application layer protocol that provides a method of communication between clients and website servers. HTTP uses port 80. HTTP is considered insecure, so it is being replaced on most websites by a secure version, called HTTPS that uses encryption from SSL/TLS for communication. However, there are still many websites that use the insecure HTTP protocol.

- **Port:** 80
- **Security:** Insecure, plaintext communication.
- **Layer (TCP/IP Model):** Application Layer

### Domain Name System (DNS)

A protocol that translates internet domain names into IP addresses. When a client computer wishes to access a website domain using their internet browser, a query is sent to a dedicated DNS server. The DNS server then looks up the IP address that corresponds to the website domain. DNS normally uses UDP on port 53. However, if the DNS reply to a request is large, it will switch to using the TCP protocol.

- **Port:** 53 (UDP/TCP)
- **Layer (TCP/IP Model):** Application Layer

## Management Protocols

The next category of network protocols is management protocols. Management protocols are used for monitoring and managing activity on a network. They include protocols for error reporting and optimizing performance on the network.

### Simple Network Management Protocol (SNMP)

A network protocol used for monitoring and managing devices on a network. SNMP can reset a password on a network device or change its baseline configuration. It can also send requests to network devices for a report on how much of the network’s bandwidth is being used up.

- **Layer (TCP/IP Model):** Application Layer

### Internet Control Message Protocol (ICMP)

An internet protocol used by devices to tell each other about data transmission errors across the network. ICMP is used by a receiving device to send a report to the sending device about the data transmission. ICMP is commonly used as a quick way to troubleshoot network connectivity and latency by issuing the “ping” command on a Linux operating system.

- **Use Case:** Troubleshooting network connectivity using `ping`.
- **Layer (TCP/IP Model):** Internet Layer

### Dynamic Host Configuration Protocol (DHCP)

Dynamic Host Configuration Protocol (DHCP) is in the management family of network protocols. DHCP is an application layer protocol used on a network to configure devices. It works with the router to assign a unique IP address to each device and provide the addresses of the appropriate DNS server and default gateway for each device.

- **Ports:** DHCP servers operate on UDP port 67 while DHCP clients operate on UDP port 68.

## Security Protocols

Security protocols are network protocols that ensure that data is sent and received securely across a network. Security protocols use encryption algorithms to protect data in transit. Below are some common security protocols.

### Hypertext Transfer Protocol Secure (HTTPS)

A network protocol that provides a secure method of communication between clients and website servers. HTTPS is a secure version of HTTP that uses secure sockets layer/transport layer security (SSL/TLS) encryption on all transmissions so that malicious actors cannot read the information contained.

- **Port:** 443
- **Security:** Uses SSL/TLS encryption.
- **Layer (TCP/IP Model):** Application Layer

### Secure File Transfer Protocol (SFTP)

A secure protocol used to transfer files from one device to another over a network. SFTP uses secure shell (SSH), typically through TCP port 22. SSH uses Advanced Encryption Standard (AES) and other types of encryption to ensure that unintended recipients cannot intercept the transmissions.

- **Technology:** Uses SSH (TCP port 22) with AES encryption.
- **Use Case:** Used often with cloud storage (uploading or downloading files).
- **Layer (TCP/IP Model):** Application Layer

**Note:** The encryption protocols mentioned do not conceal the source or destination IP address of network traffic. This means a malicious actor can still learn some basic information about the network traffic if they intercept it.

### Network Address Translation (NAT)

The devices on your local home or office network each have a private IP address that they use to communicate directly with each other. However, in order for the devices with private IP addresses to communicate with the public internet, they need to have a single public IP address that represents all devices on the LAN to the public. For outgoing messages, the router can replace a private source IP address with its public IP address and perform the reverse operation for responses. This process is known as Network Address Translation (NAT) and it generally requires a router or firewall to be specifically configured to perform NAT.

- **Function:** Allows devices with private IP addresses to communicate with the public internet using a single public IP address.
- **Layer (TCP/IP Model):** NAT is a part of layer 3 (internet layer) and layer 4 (transport layer) of the TCP/IP model.

### Address Resolution Protocol (ARP)

By now, you are familiar with IP and MAC addresses. You’ve learned that each device on a network has a public IP address, a private IP address, and a MAC address that identify it on the network. A device’s IP address may change over time, but its MAC address is permanent because it is unique to a device’s network interface card. The MAC address is used to communicate with devices within the same network, but sometimes, the MAC address is unknown. This is why the Address Resolution Protocol (ARP) is needed. ARP is mainly a network access layer protocol in the TCP/IP model used to translate the IP addresses that are found in data packets into the MAC address of the hardware device.

Each device on the network performs ARP and keeps track of matching IP and MAC addresses in an ARP cache.

- **Function:** Translates IP addresses into MAC addresses.
- **Layer (TCP/IP Model):** Network Access Layer
- **Note:** ARP does not have a specific port number since it is a layer 2 protocol and port numbers are associated with the layer 7 application layer.

### Telnet

Telnet is an application layer protocol that is used to connect with a remote system. Telnet sends all information in clear text. It uses command line prompts to control another device similar to secure shell (SSH), but Telnet is not as secure as SSH.

- **Security:** Insecure, plaintext communication.
- **Port:** 23
- **Layer (TCP/IP Model):** Application Layer

### Secure Shell (SSH)

Secure shell protocol (SSH) is used to create a secure connection with a remote system. This application layer protocol provides an alternative for secure authentication and encrypted communication.

- **Security:** Provides secure authentication and encrypted communication.
- **Port:** 22
- **Use Case:** Replacement for less secure protocols, such as Telnet.
- **Layer (TCP/IP Model):** Application Layer

### Post Office Protocol (POP)

Post office protocol (POP) is an application layer (layer 4 of the TCP/IP model) protocol used to manage and retrieve email from a mail server. POP3 is the most commonly used version of POP. Many organizations have a dedicated mail server on the network that handles incoming and outgoing mail for users on the network. User devices will send requests to the remote mail server and download email messages locally. If you have ever refreshed your email application and had new emails populate in your inbox, you are experiencing POP and internet message access protocol (IMAP) in action.

- **Ports:**
  - Unencrypted, plaintext authentication: TCP/UDP port 110
  - Encrypted emails use Secure Sockets Layer/Transport Layer Security (SSL/TLS) over TCP/UDP port 995.
- **Layer (TCP/IP Model):** Application Layer
- **Limitations:** Mail has to finish downloading on a local device before it can be read. After downloading, the mail may or may not be deleted from the mail server, so it does not guarantee that a user can sync the same email across multiple devices.

### Internet Message Access Protocol (IMAP)

IMAP is used for incoming email. It downloads the headers of emails and the message content. The content also remains on the email server, which allows users to access their email from multiple devices.

- **Ports:**
  - Unencrypted: TCP port 143
  - Encrypted (TLS): TCP port 993
- **Layer (TCP/IP Model):** Application Layer
- **Advantages:** Allows users to partially read email before it is finished downloading. Since the mail is kept on the mail server, it allows a user to sync emails across multiple devices.

### Simple Mail Transfer Protocol (SMTP)

Simple Mail Transfer Protocol (SMTP) is used to transmit and route email from the sender to the recipient’s address. SMTP works with Message Transfer Agent (MTA) software, which searches DNS servers to resolve email addresses to IP addresses, to ensure emails reach their intended destination.

- **Ports:**
  - Unencrypted: TCP/UDP port 25
  - Encrypted (TLS): TCP/UDP port 587
- **Layer (TCP/IP Model):** Application Layer
- **Note:** The TCP port 25 is often used by high-volume spam. SMTP helps to filter out spam by regulating how many emails a source can send at a time.
