
This document describes simulated attack scenarios used in the project and how Wazuh detects them.

---

## 1. Brute Force SSH Attack (Linux Agent)

### Scenario
An attacker repeatedly tries to guess SSH credentials on a Linux machine.

### Attack Simulation

![SSH Brute Force Alert](https://github.com/abdelrahman0x01/Centralized-Security-Monitoring-and-Threat-Detection-using-Wazuh-SIEM/blob/main/images/ssh_bruteforce.png?raw=true)

### Detection in Wazuh
- Repeated authentication failures in /var/log/auth.log
- Multiple failed login events from same IP

### Alert Trigger
- Rule: 5760 (sshd authentication failure)
- Threshold-based alert (multiple failures)
  ![Active_response](https://github.com/abdelrahman0x01/Centralized-Security-Monitoring-and-Threat-Detection-using-Wazuh-SIEM/blob/main/images/Active_response.png?raw=true)

---

## 2. File Integrity Monitoring (FIM)

###  Scenario
Unauthorized modification of sensitive system files.

###  Attack Simulation
- mkdir /root/z/
- touch /root/z/1.txt
- rm -r /root/z/1.txt

### Detection in Wazuh
- File checksum change detected
- Real-time FIM alert
  ![FIM](https://github.com/abdelrahman0x01/Centralized-Security-Monitoring-and-Threat-Detection-using-Wazuh-SIEM/blob/main/images/FIM.png?raw=true)

---

## 3. Malware Download Detection

### Scenario
A user downloads a suspicious program.

### Attack Simulation
Download EICAR test file:
https://secure.eicar.org/eicar.com

### Detection in Wazuh
- File hash checked via VirusTotal integration
- Suspicious file creation event

### Alert Trigger
- VirusTotal API match = malicious
- Logs monitoring
  ![virustotal](https://github.com/abdelrahman0x01/Centralized-Security-Monitoring-and-Threat-Detection-using-Wazuh-SIEM/blob/main/images/Virustotal%20API%20integration.png?raw=true)

---



