# OSI vs TCP/IP Models – Networking Notes

## OSI Model (Open Systems Interconnection)

The OSI model is a **theoretical reference model** that standardizes network functions into **7 layers**. Each layer has a specific role in the communication process.

## Who created OSI ?
- Full form: **Open Systems Interconnection**  
- **Created by:** ISO (International Organization for Standardization) in 1984  
- **Purpose:** Standardize networking concepts; theoretical model, **not a protocol**  
- **Usage:** Learning, troubleshooting, vendor-neutral framework

# 7 Layers of OSI Model

## 1. Physical Layer
- Transmits raw bits (0s and 1s) over physical media  
- Media: Cables, switches, Wi-Fi signals  
- **Example:** Ethernet cables, Wi-Fi signals  

## 2. Data Link Layer
- Creates frames and handles MAC addresses  
- Performs error detection (CRC)  
- **Example:** Switch, Ethernet, ARP  

## 3. Network Layer
- Creates packets and handles IP addressing & routing  
- **Example:** Routers, IP, ICMP (ping)  

## 4. Transport Layer
- Provides end-to-end communication  
- Ensures reliability (TCP) or fast delivery (UDP)  
- **Example:** TCP, UDP, Port numbers  

## 5. Session Layer
- Establishes, maintains, and terminates sessions  
- **Example:** NetBIOS, RPC  

## 6. Presentation Layer
- Translates, encrypts, and compresses data  
- **Example:** SSL/TLS encryption, JPEG, GIF formats  

## 7. Application Layer
- Closest to the user; where applications interact with the network  
- **Example:** HTTP, HTTPS, FTP, SMTP, DNS


### 7 Layers of OSI

| Layer No. | Layer Name        | Function                                         | Examples                   |
|-----------|-----------------|-------------------------------------------------|---------------------------|
| 7         | **Application**  | Provides network services to applications      | HTTP, HTTPS, FTP, SMTP, DNS |
| 6         | **Presentation** | Data translation, encryption, compression       | SSL/TLS, JPEG, GIF        |
| 5         | **Session**      | Establishes, manages, and terminates sessions  | NetBIOS, RPC              |
| 4         | **Transport**    | End-to-end communication, reliability           | TCP, UDP, Port numbers    |
| 3         | **Network**      | Routing, logical addressing                     | IP, ICMP, Routers         |
| 2         | **Data Link**    | Frames, MAC addresses, error detection          | Ethernet, Switch, ARP     |
| 1         | **Physical**     | Transmission of raw bits over physical medium  | Cables, Wi-Fi signals     |

---
# TCP/IP model

## Who created TCP/IP Model ?

- Full form: **Transmission Control Protocol / Internet Protocol**  
- **Created by:** ARPANET researchers (1970s-1980s), key people: Vinton Cerf & Robert Kahn  
- **Governed by:** IETF (Internet Engineering Task Force)  
- **Purpose:** Real-world networking, Internet communication  
- **Includes:** TCP, IP, UDP, HTTP, DNS, etc.

# 4 Layers of TCP/IP Model

## 1. Network Access / Link Layer
- Combines Physical + Data Link layers of OSI  
- Handles physical transmission and framing  
- **Example:** Ethernet, Wi-Fi, ARP  

## 2. Internet Layer
- Maps to OSI Network layer  
- Handles IP addressing and routing  
- **Example:** IP, ICMP (ping)  

## 3. Transport Layer
- Maps to OSI Transport layer  
- Provides end-to-end communication  
- Handles TCP/UDP and port numbers  
- **Example:** TCP, UDP  

## 4. Application Layer
- Combines OSI Session, Presentation, and Application layers  
- Provides network services to applications  
- **Example:** HTTP, HTTPS, FTP, DNS, SMTP  

---

| Layer Name       | Function                                   | OSI Layer Mapping        | Examples               |
|-----------------|-------------------------------------------|-------------------------|-----------------------|
| **Application**  | Handles application, presentation, session | OSI 5,6,7               | HTTP, HTTPS, FTP, DNS |
| **Transport**    | Provides end-to-end communication         | OSI 4                   | TCP, UDP, Ports       |
| **Internet**     | Logical addressing, routing               | OSI 3                   | IP, ICMP              |
| **Network Access / Link** | Physical transmission, framing     | OSI 1,2                 | Ethernet, Wi-Fi       |

---

- IP = “Where to send” → finds the path to destination.
- TCP = “How to send reliably” → ensures data arrives intact and in order.
- Together (TCP/IP) → Internet works: IP routes packets, TCP makes sure they’re received correctly.

# 🔹 OSI vs TCP/IP Comparison

| Feature       | OSI Model (7 Layers)               | TCP/IP Model (4 Layers)             |
|---------------|-----------------------------------|------------------------------------|
| Model Type    | Theoretical / Reference Model      | Practical / Implementation Model    |
| Layers        | 7 (Physical → Application)         | 4 (Link → Application)             |
| Usage         | Study, teaching, conceptual framework | Real-world networking & Internet |
| Examples      | Switch = Layer 2, Router = Layer 3 | Internet works fully on TCP/IP     |

---
![OSIvsTcP](networking/osivstcp.jpeg)

# Summary
- **OSI:** Theory model with 7 layers for detailed understanding  
- **TCP/IP:** Practical model with 4 layers used on the Internet  
- Both models map to each other; TCP/IP is what the Internet uses  
- Understanding OSI helps in troubleshooting and learning networking concept

# TCP vs UDP in Transport layer

## Introduction
- **TCP (Transmission Control Protocol)** → Reliable, connection-oriented protocol.  
- **UDP (User Datagram Protocol)** → Fast, connectionless protocol.  

---

## TCP Header Structure
- Source Port
- Destination Port
- Sequence Number
- Acknowledgment Number
- Flags (SYN, ACK, FIN, RST, PSH, URG)
- Window Size
- Checksum
- Urgent Pointer

---

## TCP Flags Explained
| Flag  | Meaning | Example |
|-------|----------|---------|
| SYN   | Start connection (synchronize) | "Hello, let's talk" |
| ACK   | Acknowledge received data | "Got it ✅" |
| FIN   | Finish connection | "Bye 👋" |
| RST   | Reset connection | "Error ❌, start over" |
| PSH   | Push data immediately | "Send quickly ⚡" |
| URG   | Urgent data | "Emergency 🚨" |

👉 TCP = Full rishta system (proposal → confirm → bye).

---

## UDP Header Structure
- Source Port
- Destination Port
- Length
- Checksum

---

## Why No Flags in UDP?
- No handshake  
- No connection management  
- No sequencing  
- Just **fast delivery** → "fire and forget" model  

👉 UDP = "Arre sunoo!" → Bhej diya, ab suno ya ignore karo, koi farq nahi.

---

## TCP vs UDP Comparison

| Feature            | TCP                         | UDP                       |
|--------------------|-----------------------------|---------------------------|
| Connection setup   | SYN/ACK handshake           | No handshake              |
| Reliability        | ACK, Retransmission         | Best effort (no ACK)      |
| Order              | Sequence numbers            | No order                  |
| Flags              | SYN, ACK, FIN, RST, PSH…    | ❌ No flags               |
| Speed              | Slower (heavy header)       | Faster (light header)     |
| Use Cases          | Web (HTTP/HTTPS), Email     | Video/Voice streaming, Gaming |

---

# Playing with TCP and UDP

## Tools Used
- **Netcat (nc / ncat)** → Send & receive TCP/UDP packets
- **Wireshark** → Packet analysis (optional but recommended)
- **curl / nslookup / dig** → For testing TCP & UDP protocols

---

## 1. TCP Server–Client Test

### Server

```bash
nc -l -p 8080
```

1. -l → Listen mode.
2. -p 8080 → Port number 8080 pe wait karega.
3. Your terminal should stucked
4. Open new terminal and use below command

### Client

```bash
nc 127.0.0.1 8080
```

5. 127.0.0.1 → Localhost (same machine).
6. Will establish connection in 8080.
7. Background TCP 3-way handshake (SYN → SYN-ACK → ACK).
8. Now if you type in server or client any thing it will show at both point.
9. For UDP connection just use -u also and same command.

## Real-World Examples
- **TCP**:  
  - HTTP (websites)  
  - HTTPS (secure websites)  
  - SMTP/IMAP (emails)  
  - FTP (file transfer)  

- **UDP**:  
  - DNS (Domain name queries)  
  - VoIP (Skype, Zoom calls)  
  - Online Gaming (PUBG, COD)  
  - Streaming (YouTube Live, Twitch)

---

# IP Addressing

## What is an IP Address?
- **IP Address (Internet Protocol Address):** A unique identifier assigned to devices in a network for communication.  
- Allows devices to **send and receive data** over networks like LAN or the Internet.  
- Types: **IPv4** and **IPv6**

---

## IPv4 (Internet Protocol version 4)
- **Format:** 32-bit address, usually written in **dotted decimal** (e.g., `192.168.1.10`)  
- **Range:** 0.0.0.0 to 255.255.255.255  
- **Number of addresses:** ~4.3 billion  
- **Classes:** A, B, C, D, E (for networks, multicast, experimental)
- **Address classes:**
- - Class A: 1.0.0.0 – 126.255.255.255 (Large networks)
- - Class B: 128.0.0.0 – 191.255.255.255 (Medium networks)
- - Class C: 192.0.0.0 – 223.255.255.255 (Small networks)
- - Class D: 224.0.0.0 – 239.255.255.255 (Multicast)
- - Class E: 240.0.0.0 – 255.255.255.255 (Experimental)
- **Example:** `192.168.1.1` (common home router IP)  
- **Pros:** Widely supported, simple  
- **Cons:** Limited address space  

---

## IPv6 (Internet Protocol version 6)
- **Format:** 128-bit address, written in **hexadecimal colon notation** (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`)  
- **Number of addresses:** ~340 undecillion (practically unlimited)  
- **Features:**  
  - Larger address space  
  - Built-in security (IPSec)  
  - No need for NAT  
  - Auto-configuration (stateless address autoconfiguration)  
- **Example:** `fe80::1ff:fe23:4567:890a`  
- **Pros:** Solves IPv4 exhaustion, better routing, security  
- **Cons:** Not universally adopted yet, complex notation  

---

## Public vs Private IP Address

| Type      | Definition | Range (IPv4) | Example | Usage |
|-----------|-----------|--------------|---------|-------|
| Public IP | Globally unique, routable over Internet | Varies | `142.250.72.14` (Google) | Access from Internet |
| Private IP | Local network only, not routable on Internet | `10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16` | `192.168.1.10` | Internal LAN, home/small office |

- **NAT (Network Address Translation)** allows private IPs to communicate over the Internet via a public IP.

---

## Localhost / Loopback Address
- **Definition:** IP that points back to the same device  
- **IPv4:** `127.0.0.1`  
- **IPv6:** `::1`  
- **Usage:**  
  - Testing local services (web servers, APIs)  
  - Debugging without external network  

---

## Key Differences Between IPv4 and IPv6

| Feature       | IPv4                     | IPv6                          |
|---------------|-------------------------|-------------------------------|
| Address Size  | 32-bit                  | 128-bit                       |
| Notation      | Dotted decimal          | Hexadecimal colon-separated  |
| Address Space | ~4.3 billion            | Practically unlimited         |
| NAT           | Often required          | Not required                  |
| Security      | Optional (IPSec)        | Built-in (IPSec mandatory)    |
| Header        | Simple                  | More complex                  |
| Deployment    | Worldwide, legacy       | Growing adoption              |

---

## Quick Commands (Linux / Windows)
- **Check IP Address:**  
  ```bash
  ip addr        # Linux
  ifconfig       # Linux (legacy)
  ipconfig       # Windows
  
# Static vs Dynamic IP Addresses

## Static IP
- **Definition:** An IP address that is **manually assigned** to a device and does **not change** over time.  
- **Assignment:** Configured manually by network administrator or in device settings.  
- **Usage Examples:**  
  - Servers (web, email, database)  
  - Network printers  
  - Routers and firewalls  
- **Advantages:**  
  - Predictable and consistent  
  - Easier to manage DNS and remote access  
- **Disadvantages:**  
  - Manual setup required  
  - Harder to scale in large networks  

---

## Dynamic IP
- **Definition:** An IP address that is **automatically assigned** by a DHCP server and **can change** over time.  
- **Assignment:** Handled automatically using **DHCP (Dynamic Host Configuration Protocol)**  
- **Usage Examples:**  
  - Home computers and smartphones  
  - Office networks for general devices  
- **Advantages:**  
  - Easy to manage  
  - Efficient use of IP addresses (reuse)  
- **Disadvantages:**  
  - IP may change, difficult for hosting servers  
  - Remote access may require extra setup  

---

## What is a Port?
- A **port** is a logical endpoint for communication on a device.  
- Every IP address can have **65,536 ports** (0-65535).  
- Helps **distinguish services** running on the same device.  
- Example: Web server runs on port `80`, SSH on `22`.

---

## Types of Ports

### 1. Well-Known Ports
- Range: 0 – 1023  
- Used by **common services and protocols**  
- Example:
  | Protocol | Port | Usage           |
  |----------|------|----------------|
  | HTTP     | 80   | Web traffic    |
  | HTTPS    | 443  | Secure web     |
  | SSH      | 22   | Secure login   |
  | FTP      | 21   | File transfer  |
  | DNS      | 53   | Domain lookup  |

### 2. Registered Ports
- Range: 1024 – 49151  
- Assigned to specific applications or vendors  
- Example: MySQL `3306`, PostgreSQL `5432`

### 3. Dynamic / Private Ports
- Range: 49152 – 65535  
- Used for **temporary connections**, often assigned by OS

---

## TCP vs UDP Ports
| Feature        | TCP                           | UDP                        |
|----------------|-------------------------------|----------------------------|
| Connection     | Connection-oriented           | Connectionless            |
| Reliability    | Reliable (ack, retransmit)   | Unreliable (faster)       |
| Use Case       | HTTP, HTTPS, FTP, SSH        | DNS, VoIP, streaming      |
| Port Example   | TCP 80 (HTTP)                | UDP 53 (DNS)              |

---

## Common Networking Ports

| Protocol  | Port | TCP/UDP | Usage                   |
|-----------|------|---------|-------------------------|
| HTTP      | 80   | TCP     | Web traffic             |
| HTTPS     | 443  | TCP     | Secure web              |
| SSH       | 22   | TCP     | Secure shell login      |
| FTP       | 21   | TCP     | File transfer           |
| SFTP      | 22   | TCP     | Secure file transfer    |
| SMTP      | 25   | TCP     | Email sending           |
| POP3      | 110  | TCP     | Email receiving         |
| IMAP      | 143  | TCP     | Email retrieval         |
| DNS       | 53   | UDP/TCP | Domain resolution       |
| DHCP      | 67/68| UDP     | IP assignment           |
| MySQL     | 3306 | TCP     | Database server         |
| PostgreSQL| 5432 | TCP     | Database server         |
| RDP       | 3389 | TCP     | Remote Desktop Protocol |

---
