# nmap-scan-report-scanme.nmap.org
A comprehensive Nmap scan analysis of scanme.nmap.org documenting open ports, services, OS detection, and network topology.

# Nmap Scan Report: scanme.nmap.org

## Executive Summary
This report documents a comprehensive network reconnaissance scan performed on **scanme.nmap.org (45.33.32.156)** on February 16, 2026. The scan was conducted using Nmap 7.98 to identify open ports, running services, operating system details, and network topology.

**Scan Duration:** 56.22 seconds  
**Target:** scanme.nmap.org (45.33.32.156)  
**Scan Type:** SYN Stealth Scan with OS detection, service version detection, and traceroute

---

## Key Findings

### Open Ports Summary
| Port | State | Service | Version |
|------|-------|---------|---------|
| 22/tcp | open | SSH | OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13 |
| 80/tcp | open | HTTP | Apache httpd 2.4.7 |
| 587/tcp | open | SMTP | tcpwrapped |
| 9929/tcp | open | nping-echo | Nping echo |
| 31337/tcp | open | tcpwrapped | - |

### Filtered Port
- **25/tcp** (SMTP) - Filtered

---

## Detailed Port Analysis

### Port 22/tcp - SSH
- **Service:** Secure Shell (SSH)
- **Version:** OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13
- **Protocol:** SSH-2.0
- **Host Keys:**
  - 1024 DSA: `ac:00:a0:1a:82:ff:cc:55:99:dc:67:2b:34:97:6b:75`
  - 2048 RSA: `20:3d:2d:44:62:2a:b0:5a:9d:b5:b3:05:14:c2:a6:b2`
  - 256 ECDSA: `96:02:bb:5e:57:54:1c:4e:45:2f:56:4c:4a:24:b2:57`
  - 256 ED25519: `33:fa:91:0f:e0:e1:7b:1f:6d:05:a2:b0:f1:54:41:56`

### Port 80/tcp - HTTP
- **Service:** Apache web server
- **Version:** Apache httpd 2.4.7 (Ubuntu)
- **Server Header:** Apache/2.4.7 (Ubuntu)
- **Supported Methods:** GET, HEAD, POST, OPTIONS
- **Title:** "Go ahead and ScanMe!"
- **Favicon:** Nmap Project favicon

### Port 587/tcp - SMTP
- **Service:** SMTP (tcpwrapped)
- **Note:** Connection could not be established for SMTP command enumeration

### Port 9929/tcp - nping-echo
- **Service:** Nping echo service
- **Purpose:** Likely a diagnostic or testing service from the Nmap suite

### Port 31337/tcp - tcpwrapped
- **Service:** tcpwrapped
- **Note:** Port 31337 is often associated with hacker culture ("elite" or "31337" speak) and may be intentionally opened for testing purposes

## images



---

## Operating System Detection

### OS Guesses (in order of confidence)
| Confidence | OS Guess |
|------------|----------|
| 95% | Linux 4.19 - 5.15 |
| 91% | Linux 4.15 |
| 90% | IPFire 2.27 (Linux 5.15 - 6.1) |
| 90% | Linux 5.4 |
| 88% | Linux 5.0 - 5.14 |
| 88% | MikroTik RouterOS 7.2 - 7.5 |
| 88% | Linux 3.11 - 4.9 |
| 88% | Linux 3.2 - 3.8 |
| 87% | Linux 5.18 |
| 87% | Linux 4.15 - 5.19 |

**Uptime:** 40.098 days (since January 7, 2026)  
**Network Distance:** 23 hops

---

## Network Topology

### Traceroute Analysis
The packet traversed 23 hops to reach the destination, with the route passing through:
1. Local network (10.21.3.98)
2. Intermediate routing infrastructure (10.x.x.x network)
3. HE.net backbone (London → Boston → New York → San Jose)
4. Lumen Technologies (formerly Level 3) interconnection
5. Linode infrastructure (equinix-sv1.linode.com)

**Latency:** Ranged from 2ms (local hop) to 323ms (final hops)

### Notable Route Observations
- Traffic routed through major internet exchanges:
  - London (HE.net core1.lon3)
  - Boston (HE.net core1.bos2)  
  - New York (HE.net core2.nyc4)
  - San Jose (HE.net core4.sjc2)
- Final destination appears hosted on Linode infrastructure in the San Jose area

---




## Security Observations

### Potential Security Considerations
1. **SSH Version:** OpenSSH 6.6.1p1 is relatively dated (released 2014) and may have unpatched vulnerabilities
2. **Multiple Open Ports:** 5 open ports increase attack surface
3. **Port 31337:** Non-standard port that could attract attention from threat actors
4. **Apache Version:** Apache 2.4.7 (Ubuntu) may have known CVEs requiring patching

### Positive Security Indicators
1. **Port 25 Filtered:** SMTP port is properly filtered, reducing spam relay risks
2. **SSH Key Authentication:** Host keys present (suggests key-based auth may be configured)
3. **tcpwrapped Services:** Some services are protected by TCP wrappers

---

## Recommendations

### For the System Administrator
1. **Update SSH:** Consider upgrading OpenSSH to the latest stable version
2. **Apache Hardening:** Review Apache configuration and apply security headers
3. **Port Justification:** Verify necessity of ports 9929 and 31337
4. **Regular Scanning:** Implement regular internal and external scans
5. **Patch Management:** Establish routine patching schedule for all services

### For Security Testing
1. **Deeper Enumeration:** Consider running vulnerability scans against discovered services
2. **Web Application Testing:** Perform directory brute-forcing on port 80
3. **SSH Analysis:** Test for weak cipher suites or authentication methods

---


