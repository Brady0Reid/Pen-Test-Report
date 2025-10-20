# 🧠 Pen-Test Report — ITT-340  
**Author:** Brady Reid  
**Updated:** Nov 3, 2024 (v2.0)  
**Course:** ITT-340 — Penetration Testing & Ethical Hacking  
**Institution:** Grand Canyon University  

---

## 🎯 Project Overview  
This project demonstrates a complete **penetration testing engagement** conducted within a controlled sandbox environment.  
It walks through every major stage of the **ethical hacking lifecycle**:

1. **Passive Reconnaissance (OSINT)** — Domain and user data collection using public tools.  
2. **Automated Reconnaissance** — Enumeration with DNSenum, TheHarvester, and Sherlock.  
3. **Network Scanning** — Port and service discovery via Nmap.  
4. **Vulnerability Assessment** — Performed using OpenVAS.  
5. **Exploitation (Lab Only)** — Demonstrated safely using Metasploit and custom payloads.  
6. **Post-Exploitation** — Discussion of persistence and mitigation strategies.  

> ⚠️ **Disclaimer:** All testing was done inside an isolated virtual lab with explicit educational permission.  
> No external systems were targeted or accessed.

---

## 🧰 Tools & Technologies  
| Category | Tools |
|-----------|-------|
| Reconnaissance | SpiderFoot · DNSenum · TheHarvester · Sherlock |
| Scanning | Nmap |
| Vulnerability Analysis | OpenVAS |
| Exploitation | Metasploit Framework · MSFVenom |
| Environment | Kali Linux · Ubuntu Server · Windows XP/Server 2003 |
| Documentation | Markdown · HTML · GitHub Pages |

---

## 📸 Evidence Gallery  
Screenshots from the lab engagement:

| Stage | Image |
|:------|:------|
| DNS Enumeration | ![DNSenum](Github1.png) |
| Sherlock Username Scan | ![Sherlock](Github2.png) |
| Nmap Port Scan | ![Nmap](Github3.png) |
| TheHarvester Results | ![Harvester](Github4.png) |
| Metasploit Setup | ![Metasploit Setup](Github5.jpg) |
| Metasploit Execution | ![Metasploit Execution](Github6.jpg) |

---

## 📊 Executive Summary  
Findings revealed:
- Outdated operating systems and services.  
- Weak or deprecated encryption protocols.  
- Cleartext transmission vulnerabilities.  
- Misconfigured access controls.

### ✅ Key Recommendations:
- Patch and replace end-of-life (EOL) systems.  
- Restrict administrative services (SSH/SMB).  
- Enforce strong encryption and password policies.  
- Implement continuous vulnerability scanning.  
- Introduce centralized log monitoring and EDR solutions.

---

## 🌐 Live HTML Report  
Experience the full formatted report (dark theme, responsive layout, and banner visuals):  
👉 **[View the Interactive Pen-Test Report](https://brady0reid.github.io/Pen-Test-Report/)**  

---

## 📬 Contact  
📧 **Email:** [bradyreid2004@gmail.com](mailto:bradyreid2004@gmail.com)  
🔗 **LinkedIn:** [Brady Reid](https://www.linkedin.com/in/brady-reidin)  
💻 **GitHub:** [@Brady0Reid](https://github.com/Brady0Reid)

---

© 2024 Brady Reid — *All testing and documentation conducted within a controlled educational environment.*
