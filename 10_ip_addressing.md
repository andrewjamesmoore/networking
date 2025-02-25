# IP Addressing and Subnetting

IP addressing is a fundamental aspect of network communication, enabling devices to identify each other on a network. Subnetting is a technique to divide a larger network into smaller, more manageable subnetworks.

## IPv4 Addresses

An IPv4 address is a 32-bit numerical identifier assigned to each device participating in a computer network that uses the Internet Protocol for communication. IPv4 addresses are typically represented in dotted decimal notation.

- **Format:** Four octets (8 bits each), separated by periods (e.g., `192.168.1.1`).
- **Address Classes:** Historically, IPv4 addresses were divided into classes (A, B, C, D, E), each with different ranges and network/host bit allocations. Classless Inter-Domain Routing (CIDR) superseded this.

  | Class | First Octet Range | Network Bits | Host Bits |
  | :---- | :---------------- | :----------- | :-------- |
  | A     | 1-126             | 8            | 24        |
  | B     | 128-191           | 16           | 16        |
  | C     | 192-223           | 24           | 8         |
  | D     | 224-239           | -            | -         |
  | E     | 240-255           | -            | -         |

- **Private IP Addresses:** IP addresses reserved for internal networks, not routable on the public internet.

  | Range                           | Description                   |
  | :------------------------------ | :---------------------------- |
  | `10.0.0.0 - 10.255.255.255`     | Large private networks        |
  | `172.16.0.0 - 172.31.255.255`   | Medium-sized private networks |
  | `192.168.0.0 - 192.168.255.255` | Small private/home networks   |

- **Special IPv4 Addresses:**
  - `0.0.0.0`: Default route, unspecified address.
  - `127.0.0.1`: Loopback address (localhost). Used for testing.
  - `255.255.255.255`: Broadcast address.
  - `169.254.0.0/16`: Automatic Private IP Addressing (APIPA). Assigned by DHCP client when a DHCP server isn't found.

## IPv6 Addresses

An IPv6 address is a 128-bit numerical identifier assigned to each device participating in a computer network that uses the Internet Protocol for communication. IPv6 addresses are typically represented in hexadecimal notation.

- **Format:** Eight groups of four hexadecimal digits, separated by colons (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`). Leading zeros within a group can be omitted. Double colons (`::`) can be used once in an address to represent a contiguous sequence of one or more groups of zero.
- **Address Types:**
  - **Unicast:** Identifies a single interface.
  - **Multicast:** Identifies a group of interfaces.
  - **Anycast:** Identifies a set of interfaces, with packets delivered to the nearest interface.
- **Link-Local Addresses:** Addresses that are only valid within a single network link (e.g., `fe80::/10`).
- **Global Unicast Addresses:** Public IPv6 addresses, routable on the internet (e.g., `2001::/16`).
- **Unique Local Addresses (ULA):** IPv6 addresses for private networks (e.g. `fc00::/7`).

## Subnetting (IPv4)

Subnetting is the practice of dividing a single IP network into two or more smaller networks, or subnets. This is done to improve network performance, security, and manageability.

- **Subnet Mask:** A 32-bit mask used to divide an IP address into network and host portions.
- **CIDR Notation:** Classless Inter-Domain Routing; represents the number of network bits in an IP address (e.g., `192.168.1.0/24`). The `/24` indicates that the first 24 bits are the network portion and the last 8 bits are for hosts.
- **Calculating Subnets:**

  1.  **Determine the number of subnets needed.**
  2.  **Determine the number of host addresses needed per subnet.**
  3.  **Calculate the number of bits required for the subnets and hosts.**
  4.  **Apply the subnet mask.**
  5.  **Determine the valid subnet addresses, broadcast addresses, and host address ranges.**

- **Example:**

  - Network: `192.168.1.0/24`
  - Subnet Mask: `255.255.255.0` (24 network bits)
  - Maximum Hosts per Subnet: 254 (2^8 - 2, excluding network and broadcast addresses)
  - To create 4 subnets we would borrow two bits from the host address range to use as subnet bits. The CIDR notation would then become /26, the new subnet mask would become 255.255.255.192.

## CIDR (Classless Inter-Domain Routing)

CIDR is an IP addressing scheme that improves the efficiency of address allocation. It replaces the old classful network addressing scheme.

- **Key Features:**
  - Eliminates the need for fixed-size network classes.
  - Allows for more flexible allocation of IP addresses.
  - Uses variable-length subnet masking (VLSM).

## Network Address Translation (NAT)

- See the separate `Network Protocols` note for detailed information on NAT.

## Address Resolution Protocol (ARP)

- See the separate `Network Protocols` note for detailed information on ARP.

---

Understanding IP addressing and subnetting is crucial for network design, administration, and troubleshooting.
