## Layer 7: Application Layer

- **Function:** Provides network access to applications and user interfaces. This is the layer closest to the end-user, acting as the interface between applications we use and the underlying network.

- **Key Concepts:**

  - **Provides Network Services:** Applications rely on this layer to initiate and manage network communications.
  - **User Interface:** Handles the presentation of data to the user.

- **Protocols & Examples:**

  | Protocol | Description                                                                                      | Example Use Case                                                            |
  | :------- | :----------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------- |
  | HTTP     | Hypertext Transfer Protocol; provides a method of communication between clients and web servers. | Web browsing (accessing web pages).                                         |
  | HTTPS    | Secure version of HTTP using SSL/TLS encryption.                                                 | Secure web transactions, e-commerce.                                        |
  | SMTP     | Simple Mail Transfer Protocol; used for sending email.                                           | Sending emails from a mail client.                                          |
  | POP3     | Post Office Protocol version 3; used for receiving email (insecure).                             | Retrieving emails from a mail server (less modern, often replaced by IMAP). |
  | IMAP     | Internet Message Access Protocol; used for managing incoming email.                              | Managing email on a server, syncing across multiple devices.                |
  | DNS      | Domain Name System; translates domain names into IP addresses.                                   | Resolving a website name (e.g., google.com) to an IP address.               |
  | FTP      | File Transfer Protocol; used for transferring files between devices (insecure).                  | Transferring files to a web server.                                         |
  | Telnet   | Remote terminal access (insecure); sends all information in clear text.                          | (Avoid use) Remote management of network devices.                           |
  | SSH      | Secure Shell; secure remote access and command execution.                                        | Securely logging into a remote server.                                      |
  | SNMP     | Simple Network Management Protocol; used for monitoring and managing network devices.            | Monitoring the status of network devices and bandwidth usage.               |
  | DHCP     | Dynamic Host Configuration Protocol; configures devices on a network and assigns IP addresses.   | Automatically assigning IP addresses to devices connecting to a network.    |

- **Data Unit:** Data
