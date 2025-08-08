# How the Dark Web Works (Backend Perspective) — Public Research Version
> This is the public, sanitized version of a private research document from [DarkRansom/docs/anonymous_web_backend.md], where sensitive operational details were removed.

This is a **publicly sanitized** document derived from a private research repository.  
All sensitive operational details, personally identifiable information (PII), and potentially misusable configurations have been removed.  
This file is intended solely for **cybersecurity research, academic study, and journalism**.


## 1. Introduction

The **dark web** is a portion of the internet intentionally hidden and accessible only through specific tools, most notably the **Tor network**.  
It is not indexed by regular search engines and uses a distinct domain structure (`.onion`).


## 2. Core Components

### 2.1 The Tor Network
- **Tor** (The Onion Router) anonymizes traffic by routing it through multiple volunteer-run servers (nodes).
- `.onion` services do not require an exit node — all communication remains inside the Tor network.

### 2.2 Onion Routing
Traffic is encrypted in multiple layers:
- **Outer layer**: for the entry node  
- **Middle layer**: for the middle node  
- **Inner layer**: for the final destination  

**Benefits**:
- No single node knows both the source and destination.
- Multi-layer encryption ensures strong anonymity.


## 3. Hidden Services (.onion)

`.onion` websites operate **exclusively inside** the Tor network.

### 3.1 Structure
A hidden service generally uses:
- A **Tor daemon** configured with hidden service settings.
- A **web server** serving content locally.
- **Hidden Service Descriptors** stored in the Tor distributed hash table (DHT).

### 3.2 Service Publication
When active, a service:
1. Chooses **Introduction Points**.
2. Creates a **descriptor** containing a public key, IP list, and signature.
3. Publishes the descriptor to the **Hidden Service Directory (HSDir)**.

### 3.3 Client Connection Process
1. Client resolves `.onion` address from the service’s public key.
2. Retrieves descriptor from the DHT.
3. Chooses a **Rendezvous Point** (RP).
4. Contacts the service via encrypted messages through an Introduction Point.
5. Both parties connect to RP, staying **fully inside Tor**.


## 4. Onion Domain Structure
- v3 `.onion` addresses are **56-character base32-encoded hashes** of the service's public key.
- Improvements:
  - Stronger cryptography (ed25519 keys)
  - Lower risk of impersonation


## 5. Backend Stack Examples

| Component         | Technology Examples             |
|-------------------|---------------------------------|
| Web Server        | Nginx, Apache                   |
| Backend Language  | Python (Flask), PHP, Node.js    |
| Database          | SQLite, PostgreSQL, MongoDB     |
| File Storage      | Encrypted volumes               |
| Email             | Privacy-focused providers via Tor |
| Messaging         | PGP encryption                  |

---

## 6. Hosting Approaches
- Self-hosted Tor nodes on hardened systems.
- Privacy-oriented hosting providers.
- Bootable anonymity-focused OS (e.g., Tails) for minimal services.
- Virtualized isolation environments.


## 7. Security Best Practices
- Use **air-gapped systems** for sensitive key storage.
- Apply **GPG/PGP encryption** for communication.
- Configure **Tor-only firewalls**.
- Rotate keys regularly.
- Use obfuscated Tor bridges if needed.


## 8. Domain Discovery
Since `.onion` sites are not indexed by Google:
- Use privacy-respecting dark web search engines.
- Check community-curated lists and directories.
- Participate in private, trust-based sharing networks.


## 9. Analytics & Monitoring
- **Self-hosted analytics** (e.g., Matomo).
- **Web server log analysis**.
- **Darknet crawlers** for mapping (research use only).


## 10. Common Legitimate Use Cases
- Whistleblower platforms.
- Privacy-preserving messaging.
- Anti-censorship tools.
- Academic and cybersecurity research.


## 11. Legal Disclaimer
Operating a Tor hidden service is **not inherently illegal**.  
Illicit content or activities may violate laws depending on jurisdiction.  
This document is for **educational and research purposes only**.


## 12. Further Reading
- [Tor Project Documentation](https://community.torproject.org/)  
- [Tor Onion Services Protocol](https://gitweb.torproject.org/torspec.git/tree/rend-spec-v3.txt)  
- [OnionScan GitHub](https://github.com/s-rah/onionscan)  


*© Public sanitized version from a private research repository.*
