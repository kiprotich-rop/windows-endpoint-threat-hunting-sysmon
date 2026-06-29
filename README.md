# Windows Endpoint Threat Hunting with Sysmon

## Project Overview

This project demonstrates endpoint threat hunting using Microsoft Sysmon to investigate Windows process creation and file creation events. The investigation focuses on reconstructing process execution, analyzing parent-child process relationships and assessing whether observed activity is malicious or benign.

Using Sysmon Event ID 1 (Process Creation) and Event ID 11 (File Creation), endpoint telemetry was analyzed to identify user activity, investigate scheduled task creation, and document findings using a SOC analyst methodology.

The investigation concluded that the observed activity was legitimate and consistent with authorized user actions performed within a controlled cybersecurity home lab.

---

## Objectives

* Investigate Sysmon Process Creation events (Event ID 1)
* Analyze File Creation events (Event ID 11)
* Reconstruct parent-child process relationships
* Investigate scheduled task creation
* Map findings to the MITRE ATT&CK framework
* Produce a professional incident investigation report

---

## Lab Environment

| Component        | Details                    |
| ---------------- | -------------------------- |
| Operating System | Windows 10 Virtual Machine |
| Hypervisor       | Oracle VirtualBox          |
| Monitoring Tool  | Sysmon                     |
| Analysis Tool    | Windows Event Viewer       |
| Supporting VM    | Kali Linux                 |

---

## Tools Used

* Sysmon
* Windows Event Viewer
* Windows Security Logs
* PowerShell
* Command Prompt
* Oracle VirtualBox
* GitHub

---

## Investigated Events

### Event ID 1 – Process Creation

Processes investigated:

* `powershell.exe`
* `whoami.exe`
* `hostname.exe`
* `ipconfig.exe`
* `cmd.exe`

---

### Event ID 11 – File Creation

Investigated file creation event:

* `svchost.exe`
* Scheduled Task:
  `C:\Windows\System32\Tasks\GoogleUserPEH`

---

## Process Tree

```text
explorer.exe
      │
      ▼
powershell.exe
      ├── whoami.exe
      ├── hostname.exe
      ├── ipconfig.exe
      └── cmd.exe
              └── dir
```

---

## MITRE ATT&CK Mapping

| Technique | Description                            |
| --------- | -------------------------------------- |
| T1059.001 | PowerShell                             |
| T1059.003 | Windows Command Shell                  |
| T1033     | System Owner/User Discovery            |
| T1082     | System Information Discovery           |
| T1016     | System Network Configuration Discovery |
| T1053.005 | Scheduled Task/Job                     |

---

## Skills Demonstrated

* Endpoint Threat Hunting
* Windows Event Log Analysis
* Sysmon Investigation
* Process Tree Analysis
* Parent-Child Process Correlation
* File Creation Analysis
* MITRE ATT&CK Mapping
* Incident Investigation
* Technical Documentation

---

## Repository Structure

```text
windows-endpoint-threat-hunting-sysmon/
│
├── README.md
├── LICENSE
├── .gitignore
├── Report/
│   └── Windows_Endpoint_Threat_Hunting_Report.pdf
├── Findings/
│   └── findings.md
├── Logs/
│   └── Sysmon_Operational.evtx
└── Screenshots/
```

---

## Project Documentation

📄 **Incident Investigation Report**

* [Windows Endpoint Threat Hunting Report](./Report/Windows_Endpoint_Threat_Hunting_Report.pdf)

---

## Conclusion

This project demonstrates practical endpoint monitoring and threat hunting techniques using Microsoft Sysmon. By analyzing process creation and file creation events, correlating parent-child relationships and investigating scheduled task activity, the project showcases the workflow of a SOC analyst performing endpoint investigations in a Windows environment.
