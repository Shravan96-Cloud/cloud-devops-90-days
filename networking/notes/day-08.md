# Networking Day 8: IP & Subnetting Cheat Sheet

## 1. IPv4 Architecture
*   **Format:** 4 octets separated by dots (e.g., `192.168.1.15`).
*   **Total Bits:** 32 bits.

## 2. Public vs. Private IPs
*   **Public:** Globally routable on the internet (e.g., `8.8.8.8` - Google DNS).
*   **Private:** Strictly for internal networks. Requires NAT to reach the internet.
    *   Class A: `10.0.0.0/8`
    *   Class B: `172.16.0.0/12`
    *   Class C: `192.168.0.0/16`
*   **Loopback:** `127.0.0.1` (Localhost).

## 3. CIDR Notation & Subnetting Examples
CIDR indicates the network mask (how many bits are locked for the network). The remaining bits determine host capacity.

*   **`/32` (Single IP):** 1 IP address total. Used for exact routing rules or firewalls.
    *   *Example:* `10.0.0.5/32` targets only that specific machine.
*   **`/24` (Standard Home/Office):** 256 IP addresses (254 usable).
    *   *Example:* `192.168.1.0/24` covers `.0` to `.255`.
*   **`/16` (Large Cloud VPC):** 65,536 IP addresses.
    *   *Example:* `10.0.0.0/16` covers `10.0.0.0` to `10.0.255.255`.
*   **`/0` (The Internet):** Refers to all IP addresses.
    *   *Example:* A routing table entry of `0.0.0.0/0` means "route to anywhere."
