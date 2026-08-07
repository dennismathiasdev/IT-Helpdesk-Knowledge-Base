# Blue Screen of Death (BSOD) Troubleshooting

## Overview

A Blue Screen of Death (BSOD) is a critical Windows error that causes the operating system to stop unexpectedly in order to prevent damage to the computer or data.

A BSOD usually displays an error code and automatically restarts the computer.

---

## Common Symptoms

- Blue screen appears suddenly.
- Computer restarts automatically.
- Windows fails to boot normally.
- Frequent system crashes.
- Error messages mentioning stop codes.

---

## Possible Causes

- Faulty RAM
- Corrupted system files
- Driver conflicts
- Windows update failure
- Hard drive problems
- Overheating
- Hardware failure
- Malware infection

---

## Troubleshooting Procedure

### Step 1: Ask the User Questions

- When did the problem start?
- Did you recently install new software?
- Did you install new hardware?
- Did Windows perform an update recently?
- Does the blue screen happen every time or occasionally?

---

### Step 2: Record the Stop Code

Example:

```
CRITICAL_PROCESS_DIED

MEMORY_MANAGEMENT

IRQL_NOT_LESS_OR_EQUAL

SYSTEM_SERVICE_EXCEPTION
```

The stop code helps identify the cause.

---

### Step 3: Boot into Safe Mode

If Windows cannot start normally:

- Hold Shift while selecting Restart.
- Navigate to:

```
Troubleshoot
→ Advanced Options
→ Startup Settings
→ Restart
```

Choose:

```
4 - Safe Mode
```

---

### Step 4: Check Windows Event Viewer

Open:

```
Event Viewer
```

Navigate to:

```
Windows Logs
→ System
```

Look for:

- Critical Errors
- Error Events
- Warning Events

---

### Step 5: Check Device Manager

Open:

```
Device Manager
```

Look for:

- Yellow warning icons
- Unknown devices
- Driver errors

Update or reinstall problematic drivers.

---

### Step 6: Run System File Checker

Open Command Prompt as Administrator.

Run:

```cmd
sfc /scannow
```

This repairs corrupted Windows system files.

---

### Step 7: Check Disk

Run:

```cmd
chkdsk /f /r
```

Restart the computer if prompted.

---

### Step 8: Check Memory

Press:

```
Windows + R
```

Type:

```
mdsched.exe
```

Restart the computer to test the RAM.

---

## Resolution

Depending on the root cause:

- Update drivers.
- Remove faulty software.
- Replace defective RAM.
- Repair Windows files.
- Install Windows updates.
- Restore the system.
- Replace failing hardware.

---

## Prevention

- Keep Windows updated.
- Install trusted drivers.
- Avoid overheating.
- Scan regularly for malware.
- Create restore points.
- Back up important files.

---

## Skills Demonstrated

- Windows Troubleshooting
- Root Cause Analysis
- Hardware Diagnostics
- Driver Management
- Command Prompt
- Customer Support

---

Created by Dennis Mathias Franklin