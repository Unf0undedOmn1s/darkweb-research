# Ransomware Leak Site Scraper Compatibility

This document lists ransomware leak sites that the current parsing logic in the **Ransomware Leak Checker Tool** can process **without additional modifications**.

The tool is designed to extract:
- Victim name / organization
- Leak date or post date
- Status (announced / partially leaked / fully leaked)
- Description text (if there is any available)
- Evidence links or sample files (if there are public)

## Fully Compatible Sites

### LockBit 3.0
- **URL format:** `http://[REDACTED]/news/`
- **Parsing:** HTML structured with `div` blocks per victim, includes title, date, and description.
- **Notes:** Static HTML layout, easy to parse. No heavy JavaScript or obfuscation.

### ALPHV / BlackCat *(site may be seized periodically)*
- **URL format:** `http://[REDACTED]/victims/`
- **Parsing:** Victim entries in table/list format; includes name, status, and sometimes countdown timers.
- **Notes:** HTML is mostly static, timers can be ignored for parsing.

### Play Ransomware
- **URL format:** `http://[REDACTED]/news/`
- **Parsing:** Simple list with victim name, date, and optional description.
- **Notes:** Occasionally uses image banners, but text is still in HTML.

### Everest Ransomware
- **URL format:** `http://[REDACTED]/victims/`
- **Parsing:** Minimal structure, consistent `h3`/`p` tags for victim details.
- **Notes:** No JavaScript-based obfuscation.

### RansomHouse
- **URL format:** `http://[REDACTED]/victims/`
- **Parsing:** Victim name + short description in HTML, occasional PDF links.
- **Notes:** PDFs are optional to parse; metadata can be extracted without them.

## Partial Compatibility

### BlackBasta
- HTML structure is parseable, but images often replace victim names (requires OCR for full automation).

### Medusa
- Table-based listing, but some entries are dynamically inserted via minimal JS. Static HTML snapshot works fine.

## Known Incompatible / Difficult Sites

### Cl0p
- Heavy use of images for victim names; parsing requires OCR or manual mapping.

### DarkAngels
- Irregular HTML structure; inconsistent formatting between posts.

### Royal Ransomware
- Posts structured inside screenshots; no plain text for names/descriptions.

## Adding New Sites
When adding a new ransomware group to the scraper:
1. Take an offline HTML snapshot of the leak site.
2. Inspect the DOM to identify selectors for:
   - Victim name
   - Post date
   - Description
3. Update the `parsers/` folder with a new `.py` file following the template.
4. Test locally with the HTML snapshot to ensure correct extraction.

## OPSEC Reminder
- Access onion sites only via Tor (ideally in a Tails + VPN environment).
- Avoid downloading any linked files unless sandboxed.
- Do not interact with threat actors or post on these sites.
