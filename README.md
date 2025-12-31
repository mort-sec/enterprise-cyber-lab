# Enterprise DFIR, SOC & Malware Analysis Lab

**Description:**
A fully virtualized, enterprise-style lab built in **VirtualBox**, designed to simulate realistic **DFIR workflows, SOC operations, malware analysis, and network security** in a professional environment. The lab showcases integration across multiple VMs with **endpoint monitoring, network segmentation, and malware containment**.

---

## Lab Components

* **pfSense VM:** Firewall, DNS server, VLAN-based network segmentation, IDS/IPS deployment, secure traffic control.
* **Kali Linux VM (Analyst Workstation):** Hosts **Splunk Server**, **Universal Forwarder**, **Velociraptor Server & Client**, ELK stack, and security automation scripts.
* **FLARE VM (Windows 10, Isolated):** Dedicated malware analysis workstation for static, dynamic, and memory analysis using **Procmon, Detect-It-Easy (DIE), PEStudio, x64dbg, Ghidra, REMnux, YARA**, and other FLARE VM tools. Fully isolated for safe malware handling.
* **Windows Server VM (Active Directory):** Domain controller providing centralized authentication, DNS, and enterprise policy enforcement.
* **Windows 11 Endpoint VM:** Domain-joined workstation with **Sysmon, Velociraptor client, and Splunk UF**, simulating enterprise endpoint telemetry.
* **Virtual Network:** Shared subnet with VLANs to replicate enterprise network architecture and monitoring workflows.

---

## Architecture Overview

```
             ┌──────────────────────────┐
             │        pfSense FW        │
             │ DNS + VLAN Segmentation  │
             └───────────┬──────────────┘
                         │
                Shared VLAN/Subnet
                         │
        ┌───────────────┴─────────────────────────┐
        │                                         │
┌─────────────┐                         ┌─────────────────┐
│ Windows AD   │ <— Splunk UF →         │ Kali Workstation │
│ Domain Ctrl  │ —— Velociraptor        │ (Splunk, Velociraptor, ELK, Scripts) │
└─────────────┘                         └─────────────────┘
                         │
                 ┌───────────────┐
                 │ Win11 Endpoint │
                 │ Sysmon + Velociraptor + Splunk │
                 └───────────────┘
                         
  ┌─────────────────────────────┐
  │ FLARE VM (Win10) Isolated   │
  │ Malware Analysis Workstation│
  └─────────────────────────────┘
```

> !!**Note:**!! FLARE VM is fully isolated to ensure safe malware execution and analysis.

---

## Skills & Workflows Demonstrated

* **Advanced DFIR & Malware Analysis:** Full malware lifecycle analysis (static, dynamic, memory). Tools: **Procmon, DIE, PEStudio, x64dbg, Ghidra, REMnux, YARA, FLARE VM utilities**.
* **SOC Operations & Threat Monitoring:** Centralized log collection, correlation, and alerting using **Splunk, ELK, Wazuh, Velociraptor**.
* **Incident Response & Threat Hunting:** Execute operational IR workflows, MITRE ATT&CK-aligned investigations, live endpoint monitoring, and telemetry analysis.
* **Enterprise Network Security:** Design and validate **pfSense firewall rules, VLANs, IDS/IPS (Snort), DNS filtering, VPN, and segmentation**.
* **Active Directory & Endpoint Management:** Domain-joined endpoints, policy enforcement, telemetry forwarding, and centralized monitoring.
* **Automation & Reporting:** Python, PowerShell, Bash for security automation, IOC generation, and executive-ready reporting.

---

## Lab Use Cases

* **Malware Analysis & IOC Generation:** Analyze suspicious binaries safely in FLARE VM and produce actionable indicators of compromise.
* **Enterprise Threat Hunting:** Identify abnormal behavior across endpoints and network traffic; simulate attack scenarios using telemetry from Splunk and Velociraptor.
* **Incident Response Simulation:** Investigate alerts, trace attacker activity, and execute response procedures across the lab environment.
* **Network & Endpoint Security Validation:** Test firewall rules, VLAN segmentation, IDS/IPS detection, and domain policy enforcement.

---

## Repository Structure

* **/diagrams/** – Network architecture and lab topology visuals
* **/reports/** – Sample DFIR reports, IOCs, and screenshots
* **/flare-vm/** – Analysis scripts, safe artifacts, configurations
* **/splunk/** – Queries, dashboards, and configuration files
* **/velociraptor/** – VQL scripts and collection artifacts
* **/pfSense/** – Firewall configurations, rules, and screenshots
* **/AD-setup/** – Active Directory setup guides and screenshots
* **README.md** – Lab documentation

---

## Important Notes

* No live malware is included; only screenshots, scripts, and safe artifacts are stored.
* Malware analysis is performed exclusively in the isolated FLARE VM to prevent contamination.
* Lab demonstrates **professional enterprise DFIR, SOC, and security operations workflows**.

---
