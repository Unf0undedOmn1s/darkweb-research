# WannaCry Ransomware
![WannaCry](images/wannacry.png)


WannaCry (also known as WanaCrypt0r 2.0) was one of the most significant ransomware outbreaks in history.  
It spread globally in May 2017, leveraging a leaked NSA exploit.  


## Overview
- **First Seen:** May 12, 2017  
- **Type:** Ransomware worm  
- **Infection Vector:** Exploited SMBv1 vulnerability (EternalBlue, CVE-2017-0144).  
- **Impact:** Infected over 200,000 systems in more than 150 countries.  


## Technical Details
- **Exploit Used:**  
  - EternalBlue exploit (leaked by Shadow Brokers, originally NSA tool).  
  - Exploits SMBv1 on Windows systems.  
- **Payload:** Encrypts files with RSA + AES.  
- **Ransom Demand:**  
  - Payment in Bitcoin.  
  - Typical ransom: ~$300–$600 USD equivalent in BTC.  
- **Kill Switch:**  
  - Malware included a hardcoded domain name check.  
  - Researcher Marcus Hutchins accidentally discovered and registered the domain, halting spread.


## Ransom Note
- Filename: `@Please_Read_Me@.txt`  
- Message: Files encrypted, ransom demand in BTC, payment instructions, deadline for doubling ransom.  


### File Extensions Targeted
- Commonly encrypted files included: `.doc`, `.xls`, `.ppt`, `.jpg`, `.zip`, `.sql`, etc.

### File Artifacts
- `tasksche.exe`, `taskdl.exe` → ransomware binaries.  
- `@Please_Read_Me@.txt` ransom note.  


## Global Impact
- **UK NHS (National Health Service)** → Hospitals disrupted, surgeries canceled.  
- **FedEx** → Shipping/logistics operations disrupted.  
- **Telefonica (Spain)** → Major telecom hit.  
- **Automotive factories** (Nissan, Renault) temporarily shut down.  


## Attribution
- **Suspected Actors:** Lazarus Group (North Korea-linked APT).  
- **Evidence:** Code similarities with earlier Lazarus malware, infrastructure overlap.  
- **US & UK governments** publicly attributed WannaCry to North Korea.  


## Law Enforcement & Response
- **Kill Switch discovery:** Stopped initial wave.  
- **Patches:** Microsoft issued emergency patches for unsupported OS (Windows XP, 2003).  
- **Blockchain tracing:** BTC collected but never fully cashed out.  
- **International attribution:** North Korea sanctioned for involvement.  


## Lessons Learned
- Importance of **patch management** (MS17-010 patch existed before outbreak).  
- Wormable ransomware can spread at internet scale in hours.  
- Inclusion of a **kill switch** shows poor OPSEC by attackers.  
- Signaled the era of **state-linked ransomware activity**.  


## References
- Microsoft Advisory MS17-010  
- US-CERT Alert (TA17-132A) – Indicators of WannaCry Ransomware  
- Europol & UK NCSC WannaCry reports  
- Public attribution statements (US, UK, Australia, Canada, New Zealand)
