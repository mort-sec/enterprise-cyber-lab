# Enterprise DFIR & SOC Virtual Lab

**Description:**
A fully virtualized, enterprise-style DFIR & SOC lab built in **VirtualBox**. This lab demonstrates realistic incident response, threat monitoring, malware analysis, and network security workflows, all within a controlled, isolated environment.

---

## Lab Components

* **pfSense VM:** Acts as the firewall, DNS server, and network segmentation tool, ensuring VLAN enforcement and secure traffic control.
* **Kali Linux VM (Analyst Workstation):** Hosts the Splunk server, Universal Forwarder, and Velociraptor server and client for SIEM and EDR monitoring.
* **FLARE VM (Windows 10, Isolated):** Dedicated malware analysis workstation with tools like Procmon, REMnux, and Ghidra, kept isolated for safe analysis.
* **Windows Server VM (Active Directory):** Functions as the domain controller, providing centralized authentication and DNS services.
* **Windows 11 Endpoint VM:** A domain-joined workstation that sends telemetry to Splunk and Velociraptor, simulating a user endpoint.
* **Virtual Network:** A shared subnet and VLANs that replicate enterprise network topology and monitoring.

---

## Architecture Overview

```
             ┌──────────────────────────┐
             │        pfSense FW        │
             │ DNS + Segmentation       │
             └───────────┬──────────────┘
                         │
                Shared VLAN/Subnet
                         │
        ┌───────────────┴─────────────────────────┐
        │                                         │
┌─────────────┐                         ┌─────────────────┐
│ Windows AD   │ <— Splunk UF →         │ Kali Workstation │
│ Domain Ctrl  │ —— Velociraptor        │ (Splunk & VR)   │
└─────────────┘                         └─────────────────┘
                         │
                 ┌───────────────┐
                 │ Win11 Endpoint │
                 │ Sysmon + VR    │
                 └───────────────┘
                         
  ┌─────────────────────────────┐
  │ FLARE VM (Win10) Isolated   │
  │ Malware Analysis Workstation│
  └─────────────────────────────┘
```

> !!**Note:**!! The FLARE VM is fully isolated to safely handle and analyze malware samples.

---

## Skills Demonstrated

* **DFIR & Malware Analysis:** Perform static and dynamic triage, memory forensics, and generate IOCs.
* **SOC & Threat Monitoring:** Create and manage SIEM dashboards, perform event correlation, and set up alerting mechanisms.
* **EDR / Endpoint Monitoring:** Use Velociraptor for live artifact collection and endpoint telemetry.
* **Network Security & Segmentation:** Implement and validate firewall rules, VLANs, and DNS filtering using pfSense.
* **Active Directory Integration:** Set up a domain-joined endpoint, centralize monitoring, and simulate enterprise environments.

---

## Lab Exercises

* **Malware Execution & Triage:** Analyze isolated samples in the FLARE VM and generate IOCs.
* **Threat Hunting & Detection:** Identify suspicious processes, lateral movement, and privilege escalation using SIEM and EDR tools.
* **Incident Response Simulation:** Capture alerts, investigate logs, and respond to simulated threats.
* **Network Security Testing:** Validate firewall rules, enforce VLAN segmentation, and ensure secure traffic flow.

---

## Repository Structure

* **/diagrams/**: Network diagrams and architecture visuals.
* **/reports/**: Sample DFIR reports, IOC tables, and screenshots.
* **/flare-vm/**: Analysis scripts and safe artifacts.
* **/splunk/**: Queries, dashboards, and configurations.
* **/velociraptor/**: VQL artifacts and collection scripts.
* **/pfSense/**: Configuration guides and screenshots.
* **/AD-setup/**: Setup instructions and screenshots.
* **README.md**: Lab overview and documentation.

---

## Important Notes

* No live malware is included in this repository. Only safe artifacts, scripts, and reports are stored.
* Always run malware analysis inside the isolated FLARE VM to prevent contamination.
* This lab is designed for educational and portfolio purposes.

---
