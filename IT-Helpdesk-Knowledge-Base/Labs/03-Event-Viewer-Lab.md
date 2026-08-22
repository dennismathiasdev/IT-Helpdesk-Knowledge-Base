# Event Viewer Investigation Lab

## Objective

Investigate a real WLAN-AutoConfig warning recorded by Windows Event Viewer and use additional network tests to determine the current state of network connectivity.

---

## Scenario

Windows Event Viewer recorded WLAN-AutoConfig warnings indicating that limited Wi-Fi connectivity had been detected and that Windows attempted automatic recovery.

The investigation focused on determining what the event reported and whether a specific underlying cause could be established from the available Windows logs.

---

## Investigation

### Step 1 - Locate the Event

Opened Windows Event Viewer using:

```text
eventvwr.msc

Navigated to:

Windows Logs → System

The relevant events were:

Source: Microsoft-Windows-WLAN-AutoConfig
Event ID: 4003
Level: Warning

Two occurrences were identified on 13 August 2026:

13/08/2026 01:02:20
13/08/2026 01:04:34
Step 2 - Examine the Event Details

The Event ID 4003 message reported:

WLAN AutoConfig detected limited connectivity, attempting automatic recovery.

Recovery Type: 4
Error Code: 0x0
Trigger Reason: 5
IP Family: 0

The same details were recorded for both Event ID 4003 occurrences.

The event confirms that Windows detected limited WLAN connectivity and attempted automatic recovery.

However, the event did not identify a specific hardware, driver, router, DHCP, DNS, or other underlying failure.

Step 3 - Review Surrounding Events

The System log was filtered around the time of the WLAN events.

The relevant timeline was:

Date/Time	Source	Event ID	Level
13/08/2026 01:02:20	WLAN-AutoConfig	4003	Warning
13/08/2026 01:04:34	WLAN-AutoConfig	4003	Warning

Other events in the surrounding period were primarily TPM information events.

No relevant DHCP, TCP/IP, DNS Client, NetworkProfile, or Wi-Fi driver event was identified that established a specific root cause.

Live Network Testing

After reviewing the historical Event Viewer warnings, the current network connection was tested using Windows command-line tools.

Test 1 - IP Configuration

Command:

ipconfig

Result:

IPv4 address present
Subnet mask present
Default gateway present

Finding:

The computer currently has a valid IPv4 network configuration.

Test 2 - Local TCP/IP Stack

Command:

ping 127.0.0.1

Result:

4 successful replies

Finding:

The local TCP/IP stack is functioning correctly.

Test 3 - Default Gateway

The default gateway identified through ipconfig was tested with:

ping [default gateway]

Result:

Successful replies

Finding:

The computer can communicate successfully with the local network gateway.

Test 4 - External Connectivity

Command:

ping 8.8.8.8

Result:

Successful replies

Finding:

The computer can currently reach an external IP address on the Internet.

Test 5 - DNS Resolution

Command:

nslookup google.com

Result:

DNS returned an address

Finding:

DNS name resolution is currently functioning correctly.

Findings

The investigation established the following:

Windows recorded two WLAN-AutoConfig Event ID 4003 warnings.
Both events reported limited connectivity and automatic recovery attempts.
The events contained an error code of 0x0.
No specific underlying cause could be established from the surrounding System log events.
The current computer has a valid IPv4 configuration.
The local TCP/IP stack responded successfully.
The default gateway responded successfully.
External IP connectivity was successful.
DNS resolution was successful.
Diagnostic Conclusion

The available evidence shows that Windows experienced limited WLAN connectivity on two occasions and automatically attempted recovery.

A specific root cause could not be established from the available Event Viewer information.

The subsequent live network tests show that the computer currently has functioning local network, Internet, and DNS connectivity.

Therefore, this investigation does not claim that a particular hardware, driver, router, DHCP, or DNS problem was identified or fixed.

If the issue occurs again, additional investigation could include reviewing Wi-Fi adapter and driver events, signal strength, router/access point logs, DHCP activity, and the timing of any future WLAN-AutoConfig events.

What I Learned

Event Viewer can provide valuable evidence when troubleshooting Windows problems.

Instead of assuming what caused a problem, I can use Event Viewer to identify the exact event source, event ID, warning level, timestamp, and available diagnostic information.

This investigation also demonstrated the importance of combining event logs with live troubleshooting commands such as ipconfig, ping, and nslookup.

The investigation showed that a warning does not automatically identify the root cause. A professional troubleshooting process should distinguish between what the evidence proves and what remains unknown.

Skills Demonstrated
Windows Event Viewer
WLAN-AutoConfig investigation
Windows network troubleshooting
ipconfig
ping
nslookup
TCP/IP troubleshooting
DNS troubleshooting
Evidence-based diagnosis
Technical documentation
Root cause analysis
Troubleshooting methodology
Tools Used
Windows 11
Event Viewer
Command Prompt
ipconfig
ping
nslookup
Evidence

The investigation was performed using the Windows Event Viewer and Command Prompt on a Windows 11 system.

No sensitive IP addresses or private network information are included in this documentation.

Completed by Dennis Mathias Franklin