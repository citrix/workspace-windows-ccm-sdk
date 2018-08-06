# Steps to use the SDK

*  Verify the CCM sdk binaries, installed on client (CCMProxy.dll and CCMSDK.dll).
*  Load the CCMSDK.DLL from installation path. Here client can use receiver registry key to get the installation path of CCM SDK binaries.
*  HKEY\_LOCAL\_MACHINE\Software\Citrix\Install\ICA Client\ InstallFolder for Admin installation
*  HKEY\_CURRENT\_USER\Software\Citrix\Install\ICA Client\ InstallFolder" for Non-Admin Installation
*  Use LoadLibrary to load the CCMSDK.DLL.
*  Use GetProcAddress to get the APIs and use accordingly, but to use the API the sdk needs to be initialized.
