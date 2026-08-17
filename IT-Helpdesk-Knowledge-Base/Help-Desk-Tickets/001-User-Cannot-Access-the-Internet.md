# Ticket #001 - User Cannot Access the Internet

## Ticket Information

**Category:** Network Connectivity

**Priority:** High

**Status:** Resolved

**Issue Type:** Internet Access

---

## User Report

The user reports that their computer is connected to the network but they cannot access websites.

---

## Initial Assessment

The issue may be related to:

- Incorrect IP configuration
- DNS resolution failure
- Network adapter problems
- Default gateway connectivity
- Router or network connectivity
- Temporary Windows network problems

---

## Troubleshooting Process

### Step 1 - Check IP Configuration

Ran:

```text
ipconfig
```

**Result:** A valid IPv4 address, subnet mask, and default gateway were present.

**Finding:** The computer has a valid network configuration.

---

### Step 2 - Test the Local TCP/IP Stack

Ran:

```text
ping 127.0.0.1
```

**Result:** Successful replies were received.

**Finding:** The local TCP/IP stack is functioning correctly.

---

### Step 3 - Test the Default Gateway

Ran:

```text
ping [Default Gateway]
```

**Result:** Successful replies were received.

**Finding:** The computer can communicate with the local network gateway.

---

### Step 4 - Test External Connectivity

Ran:

```text
ping 8.8.8.8
```

**Result:** Successful replies were received.

**Finding:** The computer can reach an external IP address.

---

### Step 5 - Test DNS Resolution

Ran:

```text
nslookup google.com
```

**Result:** DNS successfully returned an address for google.com.

**Finding:** DNS resolution is functioning correctly.
---

## Diagnostic Conclusion

All network connectivity tests completed successfully.

The computer had:

- Valid IP configuration
- Working TCP/IP
- Connectivity to the local gateway
- External IP connectivity
- Working DNS resolution

No network failure could be reproduced during this troubleshooting session.

If the user were still unable to access a particular website, the next investigation would focus on the browser, proxy configuration, firewall/security software, or the specific website/service.

---

## Tools Used

- Windows Command Prompt
- `ipconfig`
- `ping`
- `nslookup`

---

## Skills Demonstrated

- Network Troubleshooting
- TCP/IP Diagnostics
- DNS Troubleshooting
- Command-Line Troubleshooting
- Root Cause Analysis
- Technical Documentation

---

Completed by Dennis Mathias Franklin

