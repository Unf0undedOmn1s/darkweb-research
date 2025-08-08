# OPSEC Guide for Dark Web Research

This guide outlines essential **Operational Security (OPSEC)** practices for accessing and researching the dark web safely. The purpose is to prevent the exposure of your real identity, location, device fingerprint, or behavioral patterns while browsing `.onion` services.


## Why OPSEC Matters

The dark web is monitored by law enforcement, contains malicious actors, and often hosts illegal content. Poor OPSEC can expose:

- Your **IP address** or real location
- Your **device fingerprint** (browser version, OS, language, etc.)
- **Behavioral patterns** (mouse usage, access time, query style)
- Your **identity** (via cookies, autofill, metadata leaks)


## Safe Access Stack

1. **Use a VPN**
   - Never access Tor directly from your ISP-assigned IP.
   - Choose a no-log VPN with obfuscated servers (e.g., ProtonVPN, Mullvad).
   - Connect to the VPN before launching the Tor browser.

2. **Use a Virtual Machine (VM)**
   - Create an isolated Linux VM (Debian/Tails/Whonix).
   - Never log in to personal accounts or use shared clipboards.
   - Host the VM on a secure device (e.g., Qubes OS, VirtualBox, VMware).

3. **Use the Tor Browser (Official)**
   - Download only from [https://www.torproject.org](https://www.torproject.org).
   - Disable JavaScript (Security → Safest mode).
   - Never resize the window or maximize the browser.

4. **Consider Tails or Whonix**
   - **Tails**: Lives on USB, forgets everything on shutdown.
   - **Whonix**: Combines gateway and workstation VMs, routed only through Tor.


## What *Not* To Do

- Do **not** use your real name, email, or personal identifiers.
- Do **not** visit `.onion` links from random paste sites or Telegram groups.
- Do **not** download files (PDFs, ZIPs, etc.) unless in a sandbox environment.
- Do **not** share screenshots without sanitizing metadata.


## Browser Hygiene

- Disable JavaScript unless necessary for viewing specific sites.
- Avoid interacting with login fields, search bars, or unknown CAPTCHA systems.
- Use bridges or pluggable transports if Tor is blocked in your country.
- Clear all Tor circuits between sessions.


## Behavioral OPSEC

- Vary your access times and routes (don't always connect at 10:00 AM).
- Avoid using real writing patterns or query styles.
- Do not try to engage in forums unless your entire persona is fabricated and separated from your real-world identity.


## Data Hygiene

- Log everything you do in encrypted notes, not on plaintext desktop files.
- Scrub downloaded HTML or screenshots of identifiable elements.
- Do not use your main machine for file analysis — use sandboxed VMs.


## Tools to Help

| Purpose              | Tool                     |
|----------------------|--------------------------|
| Encrypted Notetaking | Standard Notes, Obsidian |
| Secure Browser       | Tor Browser              |
| VMs                  | VirtualBox, Qubes, Whonix|
| Packet Filtering     | Wireshark, tcpdump       |
| File Metadata Cleanup| MAT2 (Metadata Anonymization Toolkit) |


## Long-Term Precautions

- Use separate identities for different categories (forums, leak sites, monitoring).
- Store all bookmarks, logs, and observations in encrypted containers (e.g., VeraCrypt).
- Consider changing Tor exit nodes or using the New Identity button frequently.
- Update your OPSEC practices regularly — attackers and governments adapt.


**Beware**: Accessing the dark web is not illegal in itself, but improper handling, accessing illicit material, or poor OPSEC can lead to real-world consequences.

**Stay anonymous. Stay safe. Think before you click.**
