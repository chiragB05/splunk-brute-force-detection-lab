# splunk-brute-force-detection-lab
Project to detect brute-force attacks using Splunk Enterprise and Universal Forwarder with Windows and Kali Linux.
# Splunk Brute Force Detection Lab

## 🔧 Lab Setup

- **2 x Windows 10 VMs** (VMware)
  - 1 as **Splunk Enterprise Server** (port 9997)
  - 1 as client with **Universal Forwarder**
- **1 x Kali Linux VM** (for attack simulation)

## 📥 Log Forwarding

- Configured `inputs.conf` on the client
- Verified logs received on the Splunk server

## 🛠 Attack Simulation

- Kali Linux → Discovered client IP using `nmap`
- Found **SMB port 445** open
- Tried brute-force via:
  - `hydra` (service not enabled)
  - `smbclient` with wrong passwords (multiple times)

## 🔎 Detection

- Used `index=*` in Splunk
- Filtered by `EventCode=4625`
- Detected multiple failed login attempts
- Validated logs for time, source, eventcode

## 📊 Tools Used

- Splunk Enterprise
- Splunk Universal Forwarder
- Kali Linux
- Nmap
- Hydra
- smbclient

## 🎯 Learning Outcome

- Setup of real-time SIEM monitoring
- Brute-force attack simulation and detection
- Understanding of Windows logs and Event IDs
