## Layer 4: Transport Layer

*   **Function:** Provides reliable and unreliable data transfer between end-points. It handles segmentation, error recovery, and flow control.

*   **Key Concepts:**
    *   **Connection-Oriented (TCP):** Establishes a connection before data transfer; ensures reliable delivery with error checking.  Uses SYN, SYN/ACK, and ACK in a three-way handshake.
    *   **Connectionless (UDP):** Sends data without establishing a connection; faster but less reliable.
    *   **Port Numbers:** Identifies specific applications or services.

*   **Protocols & Examples:**

    | Protocol | Description                                                                                                     | Example Use Case                                                                                                                                                                       |
    | :------- | :-------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
    | TCP      | Transmission Control Protocol; provides reliable, ordered, and error-checked delivery of data.                 | Web browsing, email, file transfer.                                                                                                                                                  |
    | UDP      | User Datagram Protocol; provides a connectionless datagram service that offers fast, but unreliable data transfer. | Streaming video, online gaming, DNS queries.                                                                                                                                         |

*   **Data Unit:** Segments (TCP), Datagrams (UDP)
