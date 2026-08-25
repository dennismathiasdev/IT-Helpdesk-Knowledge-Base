# User Account & Password Reset Lab

## Objective

Investigate a common Help Desk scenario involving a Windows local user account and password reset.

The objective is to demonstrate how an IT Support technician can identify a local user account, verify its status, inspect account information, and understand the correct procedure for handling a password reset.

---

## Scenario

A user contacts the Help Desk because they are unable to sign in to their Windows computer.

The technician needs to determine whether the local user account exists, whether the account is active, and whether any account or password settings could contribute to the sign-in problem.

The investigation focuses on account verification and safe administrative procedures.

---

## Investigation

### Step 1 - Open Computer Management

Opened Computer Management using:

```text
compmgmt.msc

Navigated to:

Local Users and Groups
→ Users

The local user accounts available on the Windows system were displayed.

The account list was reviewed without deleting, disabling, or modifying any accounts.

Step 2 - Identify the User Account

The user account being investigated was located in the Users folder.

The account properties were reviewed to determine whether the account was active and whether any account restrictions were configured.

The account was found to be active.

No account was deleted or disabled during the investigation.

Step 3 - List Local User Accounts

Command Prompt was opened and the following command was used:

net user

Example result:

User accounts for \\COMPUTER

-------------------------------------------------------------------------------
Administrator
DefaultAccount
Dennis
Guest
WDAGUtilityAccount
The command completed successfully.

The command successfully displayed the local user accounts configured on the computer.

Step 4 - Inspect the User Account

The following command was used to inspect the local user account:

net user Dennis

Example result:

User name                    Dennis
Full Name                    Dennis Mathias Franklin
Comment
User's comment
Country/region code          000 (System Default)
Account active               Yes
Account expires              Never

Password last set            08/20/2026 12:15:00 AM
Password expires             Never
Password changeable          08/20/2026 12:15:00 AM
Password required            Yes
User may change password     Yes

Local Group Memberships      *Administrators
Global Group memberships    *None
The command completed successfully.

The example output indicates that the account is active, requires a password, and belongs to the local Administrators group.

The actual values on a Windows computer may differ.

Step 5 - Review the Account Status

The following account properties are particularly useful during Help Desk troubleshooting:

Account active
Account expires
Password last set
Password expires
Password required
User may change password
Local Group Memberships

These properties can help a technician determine whether an account restriction may be contributing to a sign-in problem.

Step 6 - Password Reset Procedure

In a real Help Desk environment, a password reset should only be performed after the user's identity and authorization have been verified.

For an authorized local Windows account, an administrator can use:

net user Dennis *

Windows then prompts the administrator to enter and confirm a new password.

The password is not displayed while it is being entered.

No actual password was recorded in this portfolio.

No password was changed during this lab.

Step 7 - Verify the Account

After an authorized password reset, the technician should verify that the account remains active.

The account can be checked again using:

net user Dennis

Example verification:

Account active               Yes
Password required            Yes
User may change password     Yes

The technician should then ask the user to sign in using the new password.

The password itself should never be documented.

Findings

The investigation demonstrated that Windows provides multiple methods for inspecting local user accounts.

Computer Management provides a graphical interface for viewing local users, while the net user command provides a command-line method for retrieving account information.

The investigation confirmed that the example account was:

Present on the system
Active
Configured to require a password
Able to change its password
A member of the local Administrators group

No account was deleted or disabled during the investigation.

No password was recorded or published.

Help Desk Password Reset Procedure

A professional password reset should follow these steps:

Confirm the user's identity.
Confirm that the user is authorized to access the account.
Determine whether the account is local, Microsoft, or organization-managed.
Follow the organization's approved password-reset procedure.
Reset the password using an authorized administrative method.
Ask the user to sign in with the new credentials.
Confirm that the user can access the required resources.
Document the ticket without recording the password.
Troubleshooting Considerations

A failed Windows sign-in does not always mean that the password is incorrect.

A technician should also consider:

Account disabled
Account expired
Password expired
Keyboard layout problems
Caps Lock or Num Lock
Network connectivity for online accounts
Microsoft account issues
Domain or organization authentication
Temporary account lockout
Windows profile problems

The technician should identify the type of account before choosing a troubleshooting method.

Diagnostic Conclusion

The investigation demonstrated how a Help Desk technician can identify and inspect a local Windows user account.

Computer Management provides a graphical method for account administration, while net user provides useful command-line account information.

The example account was active and configured to require a password.

A password reset should only be performed after the user's identity and authorization have been verified.

No actual password was changed during this lab.

What I Learned

I learned how Windows local user accounts can be investigated using Computer Management and Command Prompt.

I learned that the net user command can provide useful information about account status, password settings, and group membership.

I also learned that password resets involve both technical and security procedures.

A Help Desk technician should verify the user's identity before resetting an account password.

Passwords must always be treated as sensitive information and should never be stored in Help Desk tickets, screenshots, GitHub repositories, or other public documentation.

Skills Demonstrated
Windows user account administration
Password reset procedures
Computer Management
Local Users and Groups
Command Prompt
net user
Account status verification
Help Desk security procedures
Identity verification
Technical documentation
Basic Windows administration
Tools Used
Windows 11
Computer Management
Command Prompt
compmgmt.msc
net user
Evidence

The investigation used Windows Computer Management and Command Prompt to demonstrate local user account inspection.

No passwords or sensitive authentication information were recorded.

Screenshots can be added later if appropriate, while ensuring that passwords, personal information, security questions, or other sensitive information are not visible.

Security Considerations

Password-related troubleshooting must always protect user credentials.

Never:

Record a user's password.
Store passwords in GitHub.
Share passwords through screenshots.
Ask users to provide passwords unnecessarily.
Publish personal account information.
Reset an account without proper authorization.

The technician should document the action taken without documenting the actual password.

Practice Note

The account information and command results shown in this document are practice/example results.

They are included so the portfolio structure can be completed now.

When practising this lab later, the example information should be replaced with the actual results from the Windows computer.

Completed by Dennis Mathias Franklin