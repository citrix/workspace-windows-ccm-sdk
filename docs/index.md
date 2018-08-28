# Programmers guide to Citrix Common Connection Manager SDK for Citrix Workspace app 1808 for Windows

CCM (Citrix Common Connection Manager) SDK provides APIs that are used to obtain the session information. The information is used in a custom application to modify the appearance.

## Requirements

### Client-Side Requirements

CCM SDK API is a part of Citrix Workspace app 1808 for Windows installation package. Install Citrix Workspace app for Windows on the client device. Ensure that the `CCMSDK.dll` and `CCMProxy.dll` (for 32-bit machine) and `CCMSDK64.dll` and `CCMProxy64.dll` (for 64-bit machine) are present in the Citrix Workspace app for Windows installation folder.

If you are using Citrix Receiver for Windows Version 4.11 and later, install the Microsoft Visual 2017 C++ Redistributable Package using the following link:

*  For x86 machine: [https://aka.ms/vs/15/release/vc_redist.x86.exe](https://aka.ms/vs/15/release/vc_redist.x86.exe)
*  For x64 machine: [https://aka.ms/vs/15/release/vc_redist.x64.exe](https://aka.ms/vs/15/release/vc_redist.x64.exe)

### Server-Side Requirements

CCM SDK requires an active ICA session between the client and the server.
