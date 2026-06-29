# Investigation Findings

## Summary

A Windows endpoint was investigated using Microsoft Sysmon to analyze process creation and file creation events.

### Key Findings

* PowerShell was launched interactively by the logged-in user.
* PowerShell spawned legitimate Windows utilities including `whoami.exe`, `hostname.exe`, `ipconfig.exe`, and `cmd.exe`.
* Parent-child process relationships were consistent with expected administrative activity.
* A scheduled task file (`GoogleUserPEH`) was created by `svchost.exe` running as `NT AUTHORITY\SYSTEM`.
* The scheduled task was assessed as legitimate and associated with normal Google software operations.

## Assessment

**Severity:** Informational

**Classification:** Benign Activity

No indicators of compromise were identified during this investigation.
