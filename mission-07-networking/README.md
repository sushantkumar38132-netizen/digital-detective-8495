# Mission 7 — How computers communicate

## 1. Task
The objective of this mission is to understand computer networking principles:
- Define and distinguish key networking concepts (LAN, MAN, WAN, DNS, Router, Protocol, Packet switching, Client-Server).
- Test network connectivity and perform domain name resolution via CLI tools (`ping`, `nslookup`).
- Understand the role of DNS in translating human-friendly names to IP addresses.
- Detail the end-to-end 5–7 step lifecycle of what occurs when a user opens a website in a browser.

---

## 2. Work completed
- **Task 7.1:** Completed the Network Concepts table defining all 8 core networking terms with real-world examples.
- **Task 7.2:** Conducted network connectivity tests (`ping`) and DNS queries (`nslookup`) against a public domain (`example.com`), recording privacy-safe observations and answering the analysis questions.
- **Task 7.3:** Wrote a comprehensive 6-step breakdown explaining how a browser client requests, receives, and displays a website from a server.

---

## 3. Commands / tools used

| Command / Tool | Purpose |
| :--- | :--- |
| `ping -c 3 <host>` | Tests network reachability and round-trip latency by sending ICMP Echo Request packets to a target host. |
| `nslookup <domain>` | Queries Domain Name System (DNS) servers to retrieve the IP address mapped to a domain name. |
| `Terminal` | Command-line environment used to execute network inspection utilities. |
| `git` | Stages, commits, and pushes networking mission documentation to GitHub. |

---

## 4. Understanding

### Task 7.1 — Explain network concepts

| Concept | Explain it in your own words | Example |
| :--- | :--- | :--- |
| **LAN (Local Area Network)** | A network covering a small, localized physical area such as a single home, classroom, or office building. | A home Wi-Fi network connecting laptops, smartphones, and a wireless printer. |
| **MAN (Metropolitan Area Network)** | A high-speed network spanning a larger geographical area such as an entire town, city, or university campus. | A municipal government fiber-optic network linking city council offices and libraries. |
| **WAN (Wide Area Network)** | A telecommunications network spanning across cities, countries, or globally by interconnecting smaller networks. | The global Internet connecting millions of private and public networks worldwide. |
| **DNS (Domain Name System)** | An internet directory service that translates human-memorable domain names into numerical IP addresses. | Resolving the domain `example.com` to its numerical IP address X. |
| **Router** | A specialized network device that forwards data packets between different computer networks based on IP destination addresses. | A home Wi-Fi router directing traffic between local LAN devices and the Internet Service Provider (ISP). |
| **Protocol** | A standardized set of rules and conventions governing how devices format, transmit, and receive data. | **HTTPS** for encrypted web browsing, or **TCP/IP** for reliable packet transmission. |
| **Packet switching** | A communication method where digital messages are broken into small, individual packets that travel independently across network paths and are reassembled at the destination. | Streaming a YouTube video or downloading a file where data chunks take different routes across the internet. |
| **Client-server** | An architecture where a requesting device (**client**) asks for resources or services, and a centralized host (**server**) processes and responds. | A web browser (**client**) requesting a webpage from a GitHub web server (**server**). |

---

### Task 7.2 — Observe network information

#### 1. Terminal Network Output (Privacy-Safe)

**Connectivity Test (`ping -c 3 example.com`):**
```text
PING example.com : 56 data bytes
64 bytes from X: icmp_seq=0 ttl=59 time=5.12 ms
64 bytes from X: icmp_seq=1 ttl=59 time=5.20 ms
64 bytes from X: icmp_seq=2 ttl=59 time=5.07 ms

--- example.com ping statistics ---
3 packets transmitted, 3 packets received, 0.0% packet loss
round-trip min/avg/max = 5.07/5.13/5.20 ms
```

**DNS Lookup (`nslookup example.com`):**
```text
Server:		8.8.8.8
Address:	8.8.8.8#53

Non-authoritative answer:
Name:	example.com
Address: 000.000.000.000
Address: 000.000.000.000
```

#### 2. Network Analysis Questions

- **What a connectivity test (`ping`) helps you check:**
  - It confirms whether a remote server is online and reachable from your computer. It measures the round-trip time and reports packet loss, indicating network reliability.
- **What information a DNS lookup displays:**
  - It shows the DNS server that handled the query `8.8.8.8`, along with the corresponding IPv4 or IPv6 addresses, associated with the queried domain name.
- **The role of DNS when entering a website name in a browser:**
  - DNS acts as the "phonebook" of the Internet. Humans find names like `github.com` easy to remember, but network hardware and routers only route traffic using numerical IP addresses. DNS resolves the textual name into the exact destination IP address so a connection can be established.

---

### Task 7.3 — What happens when you open a website?

When a user opens a web browser and navigates to a URL such as `https://example.com`, the following 6 steps occur

1. **User Input & URL Parsing:** The user types the web address into the browser (**client**). The browser identifies the communication **protocol** `HTTPS` and the domain name `example.com`.
2. **DNS Lookup:** The client queries a **DNS** resolver server to translate `example.com` into its destination numerical IP address.
3. **Establishing Connection & Routing:** The client establishes a secure TCP/IP connection (and TLS encryption handshake) with the server at that IP. Network **routers** forward data packets along optimal paths across the internet between the client and host.
4. **Sending the HTTP Request:** Using the HTTPS **protocol**, the client browser sends an encrypted HTTP `GET` request packet asking the server for the webpage assets.
5. **Server Processing & Response:** The remote web **server** processes the request, locates the requested HTML, CSS, JavaScript, and image resources, and transmits them back to the client as an HTTP `200 OK` response stream divided into packets.
6. **Reassembly & Rendering:** The client browser receives and reassembles the incoming packets, parses the HTML/CSS markup, executes JavaScript, and renders the interactive webpage visually on the user's screen.

---

## 5. Difficulties faced
- Ensuring private local network information was not exposed in the documentation.
- Differentiating between the role of a physical router and DNS.

---

## 6. How I resolved them
- Sanitized all terminal command outputs and used public domain targets and public DNS resolvers (`8.8.8.8`).
- Clarified the networking model: DNS discovers **where** to go (translating domain to IP), while routers determine **how** the packets travel across networks to get there.

---

## 7. Evidence / files
- N/A

---

## 8. Commit details
- **Commit Message:** `Explain networking concepts and website communication`
- git commit -m "Explain networking concepts and website communication"