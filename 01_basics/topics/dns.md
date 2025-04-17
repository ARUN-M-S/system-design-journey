# 🌐 DNS (Domain Name System)

## 🧠 What is DNS?

The **Domain Name System (DNS)** is like the internet’s phonebook. When you type a website like `www.google.com`, DNS helps translate that human-readable domain into an IP address like `142.250.190.78` which computers use to identify each other on the network.

---

## 📦 Real-Life Analogy

Imagine you want to visit your friend's house, but you only know their name—not the address. So, you look into a **phonebook** (or your contact list) to find the address. DNS plays that same role on the internet.

---

## 🔁 How DNS Works (Step-by-Step)

1. **User Request**: You type `www.google.com` into your browser.
2. **Check Cache**: Browser or OS checks if IP is cached.
3. **Ask Recursive Resolver**: If not cached, the request goes to a DNS Resolver.
4. **Root Server**: Resolver queries the root server (returns TLD info).
5. **TLD Server**: Resolver queries the TLD server (`.com`, `.net`, etc.).
6. **Authoritative DNS Server**: It finally returns the actual IP of the domain.
7. **Response Back**: IP is sent back to your browser.
8. **Website Loads**: Now your browser uses the IP to connect and load the site.

---

## 🖼️ Diagram: DNS Flow

```plaintext
+-----------+       +-------------+       +------------+       +------------------+       +---------------------+
|   Client  | --->  | DNS Resolver| --->  | Root Server| --->  | TLD Name Server  | --->  | Authoritative Server|
+-----------+       +-------------+       +------------+       +------------------+       +---------------------+
        <--------------------------- DNS Response (IP) --------------------------------------<
## 🧰 Types of DNS Servers
Recursive Resolver: Gets the DNS data for you.

Root Name Server: First step in resolving a domain.

TLD Server: Handles top-level domains like .com, .org.

Authoritative Server: Knows the actual IP of the requested domain.

## 🚀 DNS Caching
To speed up the process, DNS responses are cached:

Browser Cache

Operating System Cache

ISP/Network Resolver Cache

🔒 DNS & Security
DNS Spoofing (Cache Poisoning): Fake IP is returned by an attacker.

DNSSEC: Adds a layer of security to ensure the response is not tampered.

✅ Summary
DNS resolves domain names to IP addresses.

It involves multiple servers to fulfill the request.

Caching greatly speeds up DNS lookups.

Security is critical due to possible spoofing attacks.