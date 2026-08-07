# Windows Update Troubleshooting

## Overview

Windows Update is responsible for downloading and installing security patches, feature updates, and bug fixes. When updates fail, the computer may become vulnerable to security risks or experience performance and compatibility issues.

---

## Common Symptoms

- Windows Update is stuck at a certain percentage.
- Updates fail repeatedly.
- Error codes appear during installation.
- Computer keeps restarting after updates.
- Windows displays "Update Failed."

---

## Possible Causes

- Poor internet connection
- Corrupted Windows Update files
- Insufficient disk space
- Damaged system files
- Windows Update service not running
- Antivirus software interference

---

## Troubleshooting Procedure

### Step 1: Ask the User

- When did the issue begin?
- What error message appears?
- Is this the first failed update?
- Has any software recently been installed?

---

### Step 2: Check Internet Connection

Confirm that the computer has a stable internet connection.

Open Command Prompt and run:

```cmd
ping google.com
```

---

### Step 3: Restart the Computer

Many update problems are resolved after a restart.

---

### Step 4: Run Windows Update Troubleshooter

Go to:

Settings → System → Troubleshoot → Other troubleshooters → Windows Update

Run the troubleshooter and apply any recommended fixes.

---

### Step 5: Check Available Disk Space

Ensure there is enough free space on the system drive for updates.

---

### Step 6: Repair Windows System Files

Open Command Prompt as Administrator.

Run:

```cmd
sfc /scannow
```

After it completes, run:

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

---

### Step 7: Retry Windows Update

Return to:

Settings → Windows Update

Click:

Check for updates

---

## Resolution

Depending on the findings:

- Restart the Windows Update service.
- Repair corrupted system files.
- Free up storage space.
- Install updates after resolving network issues.
- Temporarily disable third-party antivirus software if appropriate.

---

## Prevention

- Keep adequate free disk space.
- Maintain a stable internet connection.
- Install updates regularly.
- Avoid interrupting update installations.

---

## Skills Demonstrated

- Windows Administration
- Windows Update Troubleshooting
- Command Prompt
- System File Repair
- Customer Support

---

Created by Dennis Mathias Franklin