# Centralized Security Monitoring and Threat Detection using Wazuh 
---

## Overview 
This lab is built around a centralized **Wazuh SIEM hub** connected to multiple endpoints to simulate a real-world SOC environment with attack and defense scenarios.

--- 
## Architecture 
The lab consists of 4 machines:
---
###  Centralized Hub (Ubuntu Server)
- Wazuh Manager  
- Wazuh Indexer (OpenSearch)  
- Wazuh Dashboard  

###  Linux Agent 1
- File Integrity Monitoring (FIM)  
- Auditd root-level monitoring  

###  Attacker Machine
- Hydra brute-force attacks  
- Network scanning (reconnaissance)  

### Windows 10 Agent
- Wazuh Agent  
- Windows Event Log monitoring  
--- 
##  Implemented Security Features 
### 1. File Integrity Monitoring (FIM) 
- Monitoring /root and sensitive directories
- Detects file creation, modification, deletion
### 2. Auditd Integration 
- Monitors root-level command execution
- Tracks system-level changes 
### 3. Vulnerability Detection
- Wazuh Vulnerability Detector enabled
- OS and package scanning
### 4. Active Response
- Brute-force detection (SSH attacks)
- Automatic blocking of attacker IPs
### 5. VirusTotal Integration
- File hash reputation analysis
- IP/domain enrichment
- Malware detection enhancement
  
  ---
## Attack Scenarios 
  - SSH brute-force attack (Hydra)
  - EICAR malware test file execution
  - Root directory modification detection
 
    
    ---
## Results 
  - Real-time alerts in Wazuh Dashboard
  - Correlated attack detection
  - Automatic threat blocking via Active Response
  - External threat intelligence via VirusTotal
    
     ---
## Tools 
  - Wazuh SIEM
  - Auditd
  - VirusTotal API
  - Hydra
  - Ubuntu / Windows Agents
      
