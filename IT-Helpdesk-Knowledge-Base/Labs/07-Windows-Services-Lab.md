# Windows Services Investigation Lab

## Objective

Investigate the Windows Update service using the Windows Services management console and PowerShell.

The objective is to understand how an IT Support technician can check a Windows service, verify its current state, inspect its configuration, and document the findings without making unnecessary system changes.

---

## Scenario

A user reports that Windows Update may not be functioning correctly.

Before making any changes, an IT Support technician should first determine whether the Windows Update service exists, whether it is currently running, and how Windows is configured to start the service.

This investigation focuses on observing and verifying the Windows Update service before making any configuration changes.

---

## Investigation

### Step 1 - Open Windows Services

Opened the Windows Services management console using:

```text
services.msc
```

The Windows Update service was located in the list of available Windows services.

The service was inspected without stopping, starting, disabling, or changing its configuration.

---

### Step 2 - Identify the Windows Update Service

The service investigated was:

```text
Windows Update
```

Service name:

```text
wuauserv
```

The Windows Update service is responsible for supporting Windows Update operations.

The service was located successfully in the Services management console.

---

### Step 3 - Review the Service Status

The Windows Update service was inspected in the Services console.

Example observed configuration used for this practice documentation:

```text
Service Name: Windows Update
Service Name (System): wuauserv
Status: Running
Startup Type: Manual
```

The service was currently running and configured with a Manual startup type in this example.

No changes were made to the service configuration.

---

### Step 4 - Verify the Service Using PowerShell

PowerShell was used to verify the Windows Update service.

Command:

```powershell
Get-Service -Name wuauserv
```

Example result:

```text
Status   Name               DisplayName
------   ----               -----------
Running  wuauserv           Windows Update
```

The result shows that the `wuauserv` service was in the `Running` state.

This provides a command-line method for verifying the service status.

---

### Step 5 - Inspect the Service Configuration

The service configuration was inspected using:

```powershell
Get-CimInstance Win32_Service -Filter "Name='wuauserv'" | Select-Object Name, State, StartMode, StartName
```

Example result:

```text
Name      State    StartMode    StartName
----      -----    ---------    ---------
wuauserv  Running  Manual       LocalSystem
```

The result shows:

* Service name: `wuauserv`
* Current state: `Running`
* Startup mode: `Manual`
* Service account: `LocalSystem`

This provides additional information beyond the basic service status.

---

## Findings

The investigation confirmed that the Windows Update service was installed and available on the system.

The service was successfully located through the Services management console.

The example PowerShell investigation showed:

```text
Service: wuauserv
State: Running
Startup Mode: Manual
```

The service configuration could be inspected without making any changes to the operating system.

The investigation also demonstrated that the Windows Services console and PowerShell can be used together to verify service information.

---

## Troubleshooting Analysis

A Windows Update problem does not necessarily mean that the Windows Update service itself is stopped.

A technician should consider the user's actual symptoms before changing a service.

For example, if Windows Update fails, additional investigation could include:

* Windows Update settings
* Windows Update history
* Windows Update error messages
* Event Viewer
* Network connectivity
* Available disk space
* Windows Update components
* Related Windows services
* System errors
* Recent Windows changes

A service should not be stopped, started, disabled, or reconfigured simply because a problem has been reported.

The technician should first collect evidence and determine whether the service is actually related to the reported problem.

---

## Diagnostic Conclusion

The Windows Update service was successfully located and inspected.

The PowerShell investigation demonstrated that the service can be checked using both its service name and its current operational state.

The example investigation showed the service in a running state with a Manual startup configuration.

No service configuration changes were performed during this lab.

The investigation demonstrates an important Help Desk principle:

> Check the current state of a system before making changes.

---

## What I Learned

Windows Services provides an important interface for investigating background processes that support Windows and installed applications.

I learned that a technician can use `services.msc` to visually inspect services and PowerShell to verify service information from the command line.

I also learned that service status alone does not automatically identify the root cause of a user's problem.

A professional troubleshooting process should:

1. Understand the user's problem.
2. Gather information.
3. Check relevant services.
4. Verify the service state.
5. Investigate related components.
6. Make changes only when the evidence supports them.
7. Verify the result after any change.

This approach helps prevent unnecessary system changes.

---

## Skills Demonstrated

* Windows Services
* Windows Update troubleshooting
* PowerShell service inspection
* Service status verification
* Service configuration inspection
* Windows troubleshooting methodology
* Evidence-based investigation
* Technical documentation
* Help Desk troubleshooting
* Basic Windows administration

---

## Tools Used

* Windows 11
* Services (`services.msc`)
* PowerShell
* `Get-Service`
* `Get-CimInstance`

---

## Evidence

The investigation used the Windows Services management console and PowerShell to inspect the Windows Update service.

The PowerShell commands demonstrated how service information can be retrieved from the command line.

No service configuration was changed during the investigation.

**Note:** The displayed command results in this version are practice/example results. They should be replaced with the actual results from the Windows system before being presented as personal evidence.

---

## Future Practice

To strengthen this lab, the commands can be run on the Windows system and the actual results can be compared with the example results above.

The actual service status, startup mode, and PowerShell output should be documented if this project is later used as evidence of hands-on work.

---

Completed by Dennis Mathias Franklin

