# 🕵️ Active and Passive Reconnaissance

Reconnaissance is the most critical phase of the kill chain. If I don't know it exists, I can't test it. This page documents the tools and techniques I rely on to map out a target.

---

## ☁️ Passive Recon (OSINT)
*Gathering information without directly interacting with the target system.*

### 🔍 Search Engines & "Google Hacking"
Before touching a terminal, I dig through the web.
- **[Google Dorks (GHDB)](https://www.exploit-db.com/google-hacking-database)**: The bible of search queries to find exposed files and portals.
- **[Shodan](https://www.shodan.io/)**: The search engine for connected devices (IoT, Servers, Webcams).
- **[Censys](https://censys.io)**: Similar to Shodan, great for finding certificates and hosts.
- **[Wayback Machine](https://archive.org/web/)**: Viewing older versions of a site to find removed pages or comments.

### 🌐 DNS & Subdomain Enumeration
Mapping the attack surface by finding hidden subdomains.
- **[crt.sh](https://crt.sh/)**: Certificate Transparency search. Often reveals subdomains before they are active.
- **[DNSDumpster](https://dnsdumpster.com/)**: A free domain research tool that can discover hosts related to a domain.
- **[dnsrecon](https://github.com/darkoperator/dnsrecon)**: My go-to script for checking NS records and zone transfers.

### 👤 Social Media & User Enum
Finding the people behind the tech.
- **[Sherlock](https://github.com/sherlock-project/sherlock)**: Hunt down social media accounts by username across social networks.
- **[theHarvester](https://github.com/laramies/theHarvester)**: Gathers emails, names, subdomains, IPs, and URLs from multiple public data sources.
- **[LinkedIn](https://www.linkedin.com)**: (Manual) Used to understand the tech stack based on employee job descriptions.

### 📋 Whois & IP Info
Understanding who owns the infrastructure.
- **[Whois.domaintools.com](https://whois.domaintools.com/)**: Good for visual historical data.
- **[BGP/ASN Lookups](https://bgp.he.net/)**: Hurricane Electric's BGP toolkit to find IP ranges owned by an organization.

---

## ⚡ Active Recon
*Directly interacting with the target. (⚠️ Warning: This generates traffic and can be detected).*

### 🗺️ Network Scanning
- **[Nmap](https://nmap.org/)**: The king of scanners. 
    - *My common command:* `nmap -sC -sV -oA scan_results <IP>`
    - *Note:* Check my [Cheat Sheets](../cheat-sheets/nmap.md) for more scripts.
- **[Masscan](https://github.com/robertdavidgraham/masscan)**: When I need to scan the entire internet (or huge ranges) fast.

### 🕸️ Web Scanners & Vulnerability Assessment
- **[Burp Suite Community](https://portswigger.net/burp)**: The essential proxy for manual web testing.
- **[FFUF](https://github.com/ffuf/ffuf)**: "Fuzz Faster U Fool" - Used for directory and file discovery.
- **[Nuclei](https://github.com/projectdiscovery/nuclei)**: A fast, template-based vulnerability scanner. (Highly recommended for bug bounties).
- **[Nikto](https://github.com/sullo/nikto)**: Old school but good for finding server misconfigurations quickly.
- **[OWASP ZAP](https://www.zaproxy.org)**: A great open-source alternative to Burp Suite.

---

## 📚 Resources & Learning Material
Where I learned these techniques:
* **[TCM Security - PEH Course](https://academy.tcm-sec.com/)**: The best practical recon course I've taken.
* **[OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)**: The standard for web recon.