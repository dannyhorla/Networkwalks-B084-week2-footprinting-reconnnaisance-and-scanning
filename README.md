# PENETRATION TESTING REPORT
## Footprinting & Network Scanning Phases

**Program:** Cybersecurity Program – NetworkWalks  
**Project:** W2-PM-FINAL  
**Author:** Adebayo Olaoluwa  
**Role:** Cybersecurity Intern  
**Batch:** B084 – NetworkWalks  
**Date:** 12 November 2026

---

## 1. Project Overview

This repository documents the practical activities completed during Week 2 of my Cybersecurity and Ethical Hacking internship at NetworkWalks.

The project covers two major penetration testing activities:

1. Footprinting and reconnaissance of the `networkwalks.com` domain using multiple Kali Linux tools.
2. Network discovery and scanning of my own local area network (LAN) using Zenmap.

These exercises demonstrate how cybersecurity professionals gather publicly available information about a target and identify active devices within an authorized network.

## 2. Scope and Authorization

The activities were performed only on:

- NetworkWalks (`networkwalks.com`), for which written permission had been secured.
- My own local LAN network.

All activities were conducted strictly for educational and research purposes.

## 3. Project Objectives

- Gather publicly available domain information.
- Identify web technologies and services.
- Examine HTTP response headers.
- Identify Web Application Firewall (WAF) technology.
- Enumerate DNS records.
- Discover active hosts on a local network.
- Identify IP and MAC addresses.
- Generate a network topology using Zenmap.
- Document findings, potential risks, and recommendations.

## 4. Tools Used

| Tool | Purpose |
|---|---|
| Kali Linux | Operating system for reconnaissance |
| WHOIS | Domain registration information |
| WhatWeb | Website technology fingerprinting |
| Nslookup | Domain-to-IP resolution |
| Curl | HTTP response header inspection |
| Wafw00f | WAF detection |
| DNSRecon | DNS enumeration |
| Zenmap | Network scanning and host discovery |
| Windows CMD | Local IP and MAC address identification |

## 5. Activities Performed

### 5.1 Footprinting and Reconnaissance

I performed reconnaissance against `networkwalks.com` using six Kali Linux tools.

**WHOIS**

Used to obtain publicly available domain registration information and identify name servers.

**WhatWeb**

Identified the following web technologies:

- WordPress 7.0.4
- WP Download Manager 3.3.58

**Nslookup**

Used to resolve the domain name to its IP address.

Result:

```bash
192.232.216.135
```

**Curl**

Used the following command to inspect HTTP response headers:

```bash
curl -I https://networkwalks.com
```

The results exposed the WordPress REST API endpoint:

```text
/wp-json/
```

**Wafw00f**

Used to identify the Web Application Firewall protecting the website.

Result:

```text
ModSecurity (SpiderLabs)
```

**DNSRecon**

Used to enumerate DNS records, including:

- NS records
- MX records
- SPF records
- TXT records
- SRV records

### 5.2 Network Scanning with Zenmap

For the second activity, I used Zenmap (Nmap GUI) to perform network discovery on my local network.

The practical involved:

1. Running `ipconfig` in Windows CMD to identify my local IP address and subnet.
2. Entering the subnet into Zenmap.
3. Selecting Ping Scan to discover active hosts.
4. Identifying active host IP and MAC addresses.
5. Opening the Topology section.
6. Enabling the topology legend.
7. Saving the network topology in PDF format.

Example host addresses recorded:

```text
192.168.43.94
192.168.43.46
```

**Note:** These are example results from the practical report. Actual network addresses and host counts should be verified against my own LAN results.

## 6. Risk Analysis and Key Findings

| # | Finding | Observation | Risk Level |
|---|---|---|---|
| 1 | Web technology information exposed | WordPress and WP Download Manager identified | Medium |
| 2 | Server IP identifiable | Domain resolved to 192.232.216.135 | Low |
| 3 | HTTP technical information exposed | HTTP headers and /wp-json/ endpoint identified | Low |
| 4 | WAF technology identifiable | ModSecurity (SpiderLabs) detected | Low |
| 5 | DNS infrastructure information exposed | DNS, mail and service records identified | Medium |
| 6 | Multiple live hosts visible | Zenmap discovered active hosts | Medium |

**Important:** These findings represent observations from reconnaissance and network discovery. They are not confirmed vulnerabilities. No exploitation or vulnerability validation was performed during these modules.

## 7. Security Recommendations

Based on the observations, I recommend the following security improvements:

1. **Review publicly exposed technology information:** Regularly review publicly visible web technologies, CMS platforms and plugins.
2. **Keep software updated:** Ensure CMS platforms, plugins and other web technologies are regularly updated.
3. **Review HTTP headers:** Identify and minimize unnecessary technical information exposed through HTTP responses.
4. **Review DNS records:** Ensure that only required information and services are publicly exposed.
5. **Configure and monitor WAF:** Keep ModSecurity enabled and properly configured.
6. **Perform regular network discovery:** Periodically scan internal networks to identify active devices.
7. **Investigate unknown devices:** Verify unexpected devices discovered during network scanning.
8. **Maintain network documentation:** Keep network topology and device information updated.
9. **Conduct authorized security testing:** Ensure all reconnaissance and scanning activities are performed with appropriate permission.

## 8. Evidence Collected

<img width="1362" height="688" alt="whois result screenshot1" src="https://github.com/user-attachments/assets/a9fcd3fa-ecf2-4eaf-8cdf-20dbe747621c" />
<img width="1365" height="683" alt="whois screenshot2" src="https://github.com/user-attachments/assets/43a6c662-d091-47d6-8e21-b58a0d0cea57" />
<img width="1360" height="676" alt="wafwoof screenshot" src="https://github.com/user-attachments/assets/030da680-fb80-4243-99ad-ef5b642d0813" />
<img width="1364" height="683" alt="whatweb screenshot" src="https://github.com/user-attachments/assets/dff6c15b-4507-4960-ac49-32932ede5b1b" />
<img width="1363" height="682" alt="dnsrecon screenshot1" src="https://github.com/user-attachments/assets/3c915e34-090f-4a10-be35-dd996b3debbd" />
<img width="1366" height="677" alt="dnsrecon screenshot2" src="https://github.com/user-attachments/assets/9483c543-e6b2-4d2d-98a6-c90a1b96c21d" />
<img width="1354" height="700" alt="nslookup screenshot" src="https://github.com/user-attachments/assets/64a6b3a0-842b-4bbd-86e8-3633eec9e8c6" />
<img width="1366" height="722" alt="zenmap scan screenshot" src="https://github.com/user-attachments/assets/e50c3d3c-1ab7-4bbe-a6ba-65ad3054d9bb" />
<img width="1363" height="694" alt="curl screenshot" src="https://github.com/user-attachments/assets/8fea81f2-4d64-435b-a6e9-76738df9b913" />

### ZENMAP TOPOLOGY PDF
[Networkwalks zenmap topology.pdf](https://github.com/user-attachments/files/34770884/Networkwalks.zenmap.topology.pdf)




## 9. Learning Outcomes

Through these activities, I gained practical experience in:

- Domain footprinting and reconnaissance.
- Website technology fingerprinting.
- DNS enumeration and analysis.
- HTTP response header inspection.
- Web Application Firewall identification.
- Network discovery and scanning.
- IP and MAC address identification.
- Network topology mapping.
- Security risk identification and documentation.
- Ethical hacking principles and authorized security testing.

## 10. Conclusion

During Week 2 of my Cybersecurity and Ethical Hacking internship at NetworkWalks, I completed practical exercises covering footprinting, reconnaissance and network scanning.

I used six Kali Linux tools to gather information about a target domain and used Zenmap to identify active hosts on my local network.

These exercises strengthened my understanding of information gathering as a fundamental phase of penetration testing.

I also learned the importance of documenting security findings, understanding potential risks and ensuring that all security assessments are conducted within an authorized scope.

## 11. Disclaimer

This repository is intended strictly for educational and research purposes.

All activities were performed on systems where written permission had been secured or on systems and networks owned by me.

Unauthorized access, scanning or testing may constitute a criminal offence. Always obtain appropriate authorization before conducting security assessments.

The author, instructors and NetworkWalks are not responsible for misuse of the information contained in this repository.

## 12. Author

**Adebayo Olaoluwa**  
Cybersecurity Intern | B084 – NetworkWalks

**LinkedIn:** [Adebayo Olaoluwa](https://www.linkedin.com/in/adebayo-olaoluwa/)

---

**Program:** Cybersecurity Program at NetworkWalks  
**Week:** 02  
**Modules Completed:**
- W2-PM1 – Multiple Kali Tools
- W2-PM5 – Zenmap Scanning

**Repository:** GitHub

