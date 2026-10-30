# Day 9: DNS and Name Resolution

## 🎯 Learning Objectives
Understand how the Domain Name System (DNS) translates human-readable domains into machine-readable IP addresses, and how to troubleshoot routing using command-line tools.

---

## 🧠 Core Concepts
*   **DNS (Domain Name System):** The "phonebook" of the internet. It translates domains (like `github.com`) into IP addresses (like `140.82.113.3`).
*   **A Record:** Maps a domain name to an IPv4 address.
*   **AAAA Record:** Maps a domain name to an IPv6 address.
*   **CNAME Record:** Maps an alias domain to another domain name (e.g., mapping `www.example.com` to `example.com`).
*   **TTL (Time to Live):** How long a DNS record is cached by a resolver before it must request a fresh update.

---

## 🛠️ Commands Practiced Today

### 1. Basic Resolution (`nslookup`)
*   `nslookup google.com`: Queries the default DNS server for the IP addresses associated with a domain. Good for quick, simple checks.

### 2. Advanced Resolution (`dig`)
*   `dig google.com`: (Domain Information Groper) Provides a detailed breakdown of DNS records.
*   **Key output sections:**
    *   **status (NOERROR/NXDOMAIN):** Tells you if the domain was found or if it doesn't exist.
    *   **ANSWER SECTION:** Shows the resolved IP addresses and the current TTL countdown for the cache.
    *   **SERVER:** Shows which DNS server provided the answer (usually operating on Port 53).

### 3. Package Installation
*   `sudo apt install bind9-dnsutils`: Installs the package containing both `nslookup` and `dig` on Ubuntu/WSL systems.
