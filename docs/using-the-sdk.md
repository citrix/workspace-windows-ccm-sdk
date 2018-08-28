# Steps to use the SDK

*  Verify that the CCM sdk binaries are installed on the client (CCMProxy.dll and CCMSDK.dll).
*  Load the CCMSDK.DLL from installation path. Here client can use Citrix Workspace app registry key to get the installation path of CCM SDK binaries.
*  HKEY\_LOCAL\_MACHINE\Software\Citrix\Install\ICA Client\ InstallFolder is the registry path for Admin installation
*  HKEY\_CURRENT\_USER\Software\Citrix\Install\ICA Client\ InstallFolder is the registry path for Non-Admin Installation
*  Use `LoadLibrary` to load the CCMSDK.DLL.
*  Use `GetProcAddress` to get the APIs and use accordingly, but to use the API the sdk needs to be initialized.
