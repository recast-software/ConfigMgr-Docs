<img style="float: right;" src="https://www.recastsoftware.com/wp-content/uploads/2021/10/Recast-Logo-Dark_Horizontal.svg"  alt="Image" height="43" width="150">

# Manufacturer Tools

ConfigMgr is a tool to manage devices, and those devices are designed and manufactured all around the world, from different vendors and they produce several models using different components, and then release different generations of those models on a regular cadence.  So how do you manage those hundreds of different variants?  With ConfigMgr of course... but you'll have to rely on those device manufacture to supply the "stuff" that CM will use take the management to the next level.

I'm going to try to keep this updated as I'm aware of new tools.  I'll be focusing on the larger manufactures, but if you find others, let me know and I'll post them.

When Possible, I've had the Vendors supply the information for below, so if it sounds like it came from them, it did. :-)  Otherwise I've copied their marketing materials to explain their tools.

## Table of Contents

- Manufacturer Supplied Tools
- Community Supplied Tools and Blog Posts
- Command Lines

## Manufacturer Supplied Tools

### Lenovo

[Enterprise Tools Landing Page](https://support.lenovo.com/us/en/solutions/ht104232) | [Blog Site](https://blog.lenovocdrt.com/) | [Documentation Library](https://docs.lenovocdrt.com/)

Lenovo Employees to follow on Twitter: Joe Parker [@joe_lenovo](https://twitter.com/joe_lenovo) | Think Deployment [@LenovoCDRT](https://twitter.com/LenovoCDRT)

- **Enterprise Deployment Solutions Portal** - centralized content for IT admins who deploy, manage and patch Lenovo ThinkPad/ThinkCentre/ThinkStation products.  Provides links to:
  - Deployment Recipe Cards  
  - MEMCM Driver Pack
  - Enterprise Client Management Forum
  - Think Deploy Blog
  - Tools for patching and managing PCs
  - Guides, whitepapers, etc.  Especially the Dock Deployment Guide

- **Lenovo System Update Suite of Tools**
  - [Lenovo System Update:](https://support.lenovo.com/us/en/solutions/ht037099#tvsu)  user-facing solution for automating Lenovo Updates  
    - Can be configured to pull from Lenovo servers or from a local repository  
  - [Update Retriever:](https://support.lenovo.com/us/en/solutions/ht037099#ur)  used by admins to manage a local repository of Lenovo Updates
    - Additional feature for downloading hardware drivers to create your own MEMCM driver pack  
  - [Thin Installer:](https://support.lenovo.com/us/en/solutions/ht037099#ti)  no-install solution for automating Lenovo Updates
    - Great for use in a task sequence or with scripts  
    - Can combine with a repository into a package deploy-able through MEMCM
- **[Lenovo Patch for MEMCM](https://www.lenovo.com/us/en/landingpage/lenovopatch/)** (annual subscription)
  - Plug-in to MEMCM console  
  - Provides access to a large 3rd party catalog of updates as well as Lenovo Updates Catalog
  - Enhanced meta data for identifying updates and their supported models
  - Smart Filter feature for grouping content
  - Ability to schedule automated publishing of content based on Smart Filters
- **Lenovo Updates Catalog**
  - [V3 Catalog](https://thinkdeploy.blogspot.com/2020/06/lenovo-updates-catalog-v3-for-sccm.html)
- **[Lenovo Commercial Vantage](https://support.lenovo.com/us/en/solutions/hf003321)**
  - Side-loadable UWP app which supports GPO customization of end user experience
  - For IT - Ability to control
    - Customize layout
    - Keep devices up to date automatically
  - For End User - Manage your PC experience
    - Customize
      - Power Settings
      - Battery Charge Threshold
      - Smart Settings
    - Protect
      - Keep your PC up to date with latest Drivers, BIOS and firmware
      - Ensure you are using safe wireless networks

- **[Think BIOS Config Tool](https://www.lenovo.com/us/en/software/think-bios-config-tool)**
  - HTA GUI application for managing BIOS settings using the Lenovo WMI BIOS interface  
  - Can generate profile of settings that can be applied in task sequence by command line
  - No, it unfortunately cannot set a supervisor password if one does not exist.

- **[Lenovo Dock Manager](https://support.lenovo.com/us/en/solutions/ht037099#dm)**
  - Client-side utility that handles updating Lenovo Dock Firmware
  - Can pull firmware updates from Lenovo Support or from a local repository
  - Local repository created and maintained using Update Retriever
  - Adds useful dock related information into WMI

### HP

[Enterprise Tools Landing Page](https://www8.hp.com/us/en/ads/clientmanagement/overview.html) | [Community / Blog Site](https://developers.hp.com/community) | [Outlet Site](http://www.hp.com/sbso/buspurchase_refurbished.html)

HP Employees to follow on Twitter: Nathan Kofahl [@nkofahl](https://twitter.com/nkofahl) | Val [@txvalp](https://twitter.com/txvalp) | Hitarthi Shah
[@hitarthiushah](https://twitter.com/hitarthiushah)

Enterprise manageability is a critical foundational need for a smoother running and more secure client PC infrastructure. Over the past several years, HP has invested significantly in the development of PC management tools. Here is an outline of HP’s most useful and most used system tools for standard and modern desktop management.

These tools are available at no cost from the [HP download library](https://www8.hp.com/us/en/ads/clientmanagement/download.html)

- **[HP Image Assistant](https://ftp.hp.com/pub/caps-softpaq/cmit/HPIA.html)**
The HP Image Assistant (HPIA) is an essential tool that provides assistance to IT System Administrators to improve the quality and security of their HP PCs running Microsoft Windows by analyzing, identifying problems, and recommending solutions.  

    Existing and new Features and benefits:

  - Frequent Releases to quickly support new Windows Builds
  - Image Assistant will analyze and report:
    - Security Issues
    - Driver Issues
    - BIOS Settings
    - Advisories & Bulletins
  - Installs missing or outdated drivers and software
  - Provides command line support for automation
    - Supports command line offline access to a company repository
  - Supports individual versions of Windows 10. Essential for Windows 10 transitions.

  HPIA can be used for driver and BIOS updates for Autopilot-registered devices in a Modern Desktop scenario when packaging the tool with Microsoft Intune. As an example, Nickolaj Andersen, on his [blog](https://msendpointmgr.com/2020/09/10/automatically-install-the-latest-hp-drivers-during-autopilot-provisioning/), outlines a process for setting up such an environment. You can find additional information at HP for the use of HPIA for driver injection, [link](https://developers.hp.com/hp-client-management/blog/driver-injection-hp-image-assistant-and-hp-cmsl-in-memcm), and driver updates, [link](https://developers.hp.com/hp-client-management/blog/using-hp-image-assistant-driver-updates-memcm), in a Microsoft Endpoint Manager Configuration Manager environment.  

- **[HP Client Management Script Library](https://developers.hp.com/hp-client-management/doc/client-management-script-library)**

  The HP Client Management Script Library (HP CMSL) is a free set of PowerShell scripts that aid IT Admins who want to automate PC Lifecycle Management tasks.  
  Features and benefits:

  - Download software, firmware, and driver updates
  - Create and maintain repositories of drivers, software, and firmware
  - Query and set BIOS settings
  - Support for BIOS updates from the cloud or a local repository
  - Set custom BIOS boot logo
  - Supports the initialization and management of HP Security features
    - HP Sure Admin – BIOS security without passwords, details on this [blog](https://developers.hp.com/hp-client-management/blog/secure-bios-hp-sure-admin-and-cmsl)
    - HP Sure Recover – secure reimaging process, details on this [blog](https://developers.hp.com/hp-client-management/blog/provisioning-and-configuring-hp-sure-recover-hp-client-management-script-library)

  The HP CMSL can be fully integrated and used in a cloud environment along with Microsoft’s Endpoint Manager/Intune. These blogs, [deploy CMSL](https://developers.hp.com/hp-client-management/blog/deploying-hp-client-management-script-library-microsoft-intune), [Manage BIOS Updates](https://developers.hp.com/hp-client-management/blog/remediating-bios-updates-microsoft-intune-proactive-remediation-and-hp-cmsl), [Mange BIOS Settings](https://developers.hp.com/hp-client-management/blog/managing-battery-health-settings-hpcmsl-and-intune), detail how to manage the BIOS from the cloud.

- **[HP BiosConfigUtility](https://ftp.hp.com/pub/caps-softpaq/cmit/HP_BCU.html)**

  The HP BIOS Configuration Utility (BCU) is a free utility that can manage BIOS settings on HP supported desktop, workstation, and notebook computers.  
  Features and benefits:

  - Read available BIOS settings and their values from a supported computer
  - Set configurable BIOS settings on a supported computer
  - Set or reset Setup Password on a supported computer
  - Replicate BIOS settings across multiple client computers
  - Obtain BIOS settings without the need to use WMI queries and methods

- **[HP Manageability Integration Kit](https://ftp.hp.com/pub/caps-softpaq/cmit/HPMIK.html)**

  The HP Manageability Integration Kit (MIK) will help speed up image creation and management of HP BIOS, security, hardware, software when managing devices through Microsoft Endpoint Manager Configuration Manager.
  Deploy the HP Manageability Integration Kit to begin enjoying these key benefits:

  - Speed Up the Basics of IT Management – Reduce the number of steps to create, deploy, and manage images, BIOS, and system security so you can focus on business.
  - Protect Data – Secure BIOS settings, set authentication and credentials requirements, enable Microsoft Device Guard, manage TPM firmware updates.
  - Manage Software – Starting with HP Client Security, IT Admins can remotely manage features supported by the software.
  - Simplifying operations – Unlock additional value from platform-specific features and manage those features from within Microsoft System Center Configuration Manager

### Dell Technologies

[Enterprise Tools Landing Page](https://www.delltechnologies.com/en-us/systems-management/client-command-suite.htm) | [Community Forum](https://www.dell.com/community/Dell-Community/ct-p/English) | [Refurbished Sale Site](https://www.dellrefurbished.com/) | [Outlet Site](https://www.dell.com/en-us/dfb/shop/refurbished-business/cp/outlet-dfb)

To solve the challenges for IT groups, Dell’s system management approach is based on four key capabilities.

- System Setup
  - Dell Command | [Deploy](https://www.dell.com/support/article/en-us/sln312414/dell-command-deploy-driver-packs-for-enterprise-client-os-deployment?lang=en) - Helps in easy driver deployment while building an image, taking the guesswork out of this process and reducing the deployment time. It provides numerous system specific drivers that have been extracted and reduced to an OS consumable state.
  - Dell Command | [Configure](https://www.dell.com/support/article/en-us/sln311302/dell-command-configure?lang=en) - DCC is a graphical user interface (GUI) tool for creating BIOS policies in a pre-OS and post-OS environment. It operates seamlessly with SCCM and VMWare Workspace ONE and is self-integrated into LANDesk and KACE to help adjust over 170 BIOS settings.
  - Dell Command | [PowerShell Provider](https://www.dell.com/support/article/en-us/sln311262/dell-command-powershell-provider?lang=en) - This tool provides more capabilities and manageability via the scripting protocol using command line interface (CLI), even in a Windows pre-install (WinPE) environment to configure BIOS settings.
- Monitor Devices
  - Dell Command | [Monitor](https://www.dell.com/support/article/en-us/sln311855/dell-command-monitor?lang=en) - DCM provides easy management of hardware by providing customers a line of sight to hardware inventory health, BIOS configurations, installed software, and warranty status.
- Manage System Updates
  - Dell Command | [Update](https://www.dell.com/support/article/en-us/sln311129/dell-command-update?lang=en) - DCU is an easy-to-use graphical user interface (GUI) tool used to update Dell client systems with the latest applications, drivers, BIOS, and firmware.
  - Dell Command | [Cloud Repository Manager](https://www.dell.com/support/article/en-us/sln322893/dell-command-cloud-repository-manager?lang=en) - DCCRM is our latest offering and is the cloud version of the on-prem repository manager. It allows users to build, manage, and share customized catalogs of the latest BIOS, driver, firmware and application updates. These catalogs help to streamline the process of finding and determining system updates needed to keep commercial client devices ready and secure. It can be accessed via Dell’s TechDirect portal. [Manual](https://dl.dell.com/topicspdf/command-cloud-repository-manager_administrator-guide4_en-us.pdf)

- Integrated Solutions
  - Dell Command | [Integration Suite for System Center](https://www.dell.com/support/article/en-us/sln311125/dell-command-integration-suite-for-system-center?lang=en) - For customers who primarily use Microsoft’s System Center Configuration Manager, DCIS integrates the major components of Dell Command Suite right into SCCM, providing native support for BIOS, drivers, applications, and firmware patches.
  - [VMware Workspace ONE Integration](https://www.delltechnologies.com/en-us/endpointsecurity/manageability.htm) - Dell Client Command Suite and Workspace ONE (WS1) together provide simplified and secure access to manage all Dell systems. You now have the key capabilities of DCCS but in a cloud-based tool, that can also manage your organization’s mobile devices.
  - Dell Command | [Intel vPro Out of Band](https://www.dell.com/support/article/en-us/sln311294/dell-command-intel-vpro-out-of-band?lang=en) - This is a unique Dell value added feature that extends Dell Client Command Suite’s capabilities to out of band devices – systems that are offline or disconnected from the OS.

### Microsoft Surface

 [Surface Landing Page](https://docs.microsoft.com/en-us/surface/) | [Microsoft Mechanics (Videos)](https://www.youtube.com/channel/UCJ9905MRHxwLZ2jeNQGIWxA)

 Microsoft Surface Employees to follow on Twitter: Carl [@CarlLuberti](https://twitter.com/CarlLuberti)

- **[Surface Deployment Accelerator](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)**  
I've read over the blog and some of the code, while it was designed for Surface Devices, the code is all available on [GitHub](https://github.com/microsoft/SurfaceDeploymentAccelerator) and you can easily use it for any device.  
- **Microsoft Surface Enterprise Management Mode [SEMM](https://docs.microsoft.com/en-us/surface/surface-enterprise-management-mode)** is a feature of Surface devices with Surface UEFI that allows you to secure and manage firmware settings within your organization. With SEMM, IT professionals can prepare configurations of UEFI settings and install them on a Surface device. In addition to the ability to configure UEFI settings, SEMM also uses a certificate to protect the configuration from unauthorized tampering or removal. What that means in a nutshell is that SEMM can be used to lock down the firmware and hardware without using passwords, rather certificates and UEFI configuration packages.  It has an MSI tool to generate packages (called "Surface UEFI Configurator") if you're doing one or two at a time or you want to test quickly, and it also has a PowerShell provider dll ("Surface UEFI Manager") and is scriptable (SEMM_PowerShell.zip from the Surface Tools for IT site) has examples) so that it can be deployed en masse via tools like SCCM.  An interesting note, you can't use a SEMM MSI package in SCCM because it installs as LOCALSYSTEM (even if you're running as a user, it still ultimately uses the LOCALSYSTEM account to stage the firmware write, which is disallowed explicitly to any account but administrators with a full, interactive logon session.....), hence why the PS provider exists.  The Configurator, PowerShell module, and script samples can be downloaded from the  [SurfaceTools for IT](https://www.microsoft.com/en-us/download/details.aspx?id=46703) page
- **Device Firmware Configuration Interface [DFCI](https://docs.microsoft.com/en-us/windows/deployment/windows-autopilot/dfci-management)**  
 With Windows Autopilot Deployment and Intune, you can manage Unified Extensible Firmware Interface (UEFI) settings after they're enrolled by using the Device Firmware Configuration Interface (DFCI). DFCI enables Windows to pass management commands from Intune to UEFI to Autopilot deployed devices. This allows you to limit end user's control over BIOS settings. For example, you can lock down the boot options to prevent users from booting up another OS, such as one that doesn't have the same security features. DFCI is still in test (planned to go live this summer, although current situations may alter that timeline somewhat), but it's the cloud analog to SEMM - a certificate is installed into the device UEFI (meaning this only supports new products right now, it isn't planned to be available to older products prior to Pro7/Laptop3/ProX right this second) from the factory, and settings can be pushed from InTune to lock down devices and the UEFI itself.  It doesn't have 100% of the capabilities of SEMM at the current moment, as we are just building this out, but if enough customers test/use and ask for the addition of features currently only found in SEMM, we can consider it as with any DCR filing.  We're trying to focus on the big line items that people generally want to approach (disable hardware like cameras and microphones, enforce secure boot, boot order lock down, etc.) versus going with 100% of the SEMM feature set right away.  This allows us to build quicker and release quicker, and potentially bring features later versus trying to get everything working correctly out of the gate, which would have delayed by who knows how long. Also of note, you may have noticed that our UEFI, and all of the features I am describing, are open source and can be used by anyone, including other OEMs (and you may notice that Hyper-V machines on Server 2019 have a familiar UEFI....).
- **Surface Data Eraser [SDE](https://docs.microsoft.com/en-us/surface/microsoft-surface-data-eraser)**  
  Microsoft Surface Data Eraser is a tool that boots from a USB stick and allows you to perform a secure wipe of all data from a compatible Surface device. A Microsoft Surface Data Eraser USB stick requires only the ability to boot from USB. The USB stick is easy to create by using the provided wizard, the Microsoft Surface Data Eraser wrapper, and is easy to use with a simple graphic interface, no command line needed. To learn more about the data wiping capabilities and practices Since most of our devices do not have removable storage, and customers may want/need verification that the NVMe format (Section 5.23) command with data purge has actually cleaned the device to, say, GDPR standards, we have a tool to do so (also used internally on devices that come back for repair / refurbish, and Windows actually does this when you use a USB key to restore a recovery image and choose to remove everything if the disk is an NVMe disk) that will log erasure and is certified (and certificates of validation of secure erase can be had on request).  The tool will wipe any shipped drive in a Surface device - it may even erase drives that the user might replace with (say, on a Laptop 3) that didn't come from Microsoft, although the guarantee of secure erase cannot be made with certification in that regard, whereas it can if the drive and unit were shipped in, or repaired to, a "factory" state using drives we would ship with the device.
- **Surface Diagnostics Toolkit [SDT](https://support.microsoft.com/en-us/surface/fix-common-surface-problems-using-the-surface-diagnostic-toolkit-f61d8d18-37a9-863d-f8d0-1982eb16f7b5)**  
  Built with advanced diagnostics, logging, and repair capabilities, SDT enables IT admins to quickly resolve hardware, software, and firmware issues in Surface devices, beginning with Surface Pro 3 and later. The solution consists of a distributable desktop application and command-line app console that ship together in Surface Tools for IT . Surface Diagnostics Toolkit comes in two flavors - a UWP app (mostly designed for guiding a user through all tests in a 1:1 fashion), and a command-line variant that can be deployed en masse to machines and resulting data collected for analysis.  The administrator can determine what tests to run, including where to output the file(s) generated to assist in discovery and analysis.  This tool also includes a "best practices analysis" pass which will by default create an output file letting you know the status of the configuration of your device compared to specific tests.  These BPA rules are built out of learnings from support and the field, as well as guidance from engineering, and are a part of this tool.
- **Project Mu [Link](https://microsoft.github.io/mu/)**  
 Project Mu is a modular adaptation of TianoCore's [edk2](https://github.com/tianocore/edk2) tuned for building modern devices using a scalable, maintainable, and reusable pattern. Mu is built around the idea that shipping and maintaining a UEFI product is an ongoing collaboration between numerous partners.
- **DFCI on Project MU [Link](https://microsoft.github.io/mu/dyn/mu_plus/DfciPkg/Docs/Dfci_Feature/)**

## Community Blog Posts | Tools

### Lenovo

- [Set Lenovo BIOS settings through Intune and PowerShell](http://www.systanddeploy.com/2019/11/set-lenovo-bios-settings-through-intune.html) [@syst_and_deploy]

### HP

- [Automatically install the latest HP drivers during Autopilot provisioning](https://msendpointmgr.com/2020/09/10/automatically-install-the-latest-hp-drivers-during-autopilot-provisioning/) [2020.9.10 @NickolajA]
- [Ryan's Tech Blog](https://ryandengstrom.com/) [@ryandengstrom]
  - Ryan manages HP's and has good info for integrating HPIA into CM Tasks.
- [Set HP BIOS Setting via Intune and PowerShell](http://www.systanddeploy.com/2019/12/set-hp-bios-settings-through-intune-and.html) [@syst_and_deploy]
- [Manage HPs with ConfigMgr CIs](https://garytown.com/hp-cmsl-configmgr-cis) [@gwblok]
- [BIOS Sledgehammer Project](https://github.com/texhex/BiosSledgehammer) [Michael Hex]
- [Deploy HP BIOS Settings Using SCCM and HP BIOS Configuration Utility](https://www.danielengberg.com/hp-bios-configuration-utility-sccm/) [@danielclasson]
- [Deploying HP BIOS Updates – a real world example](https://smsagent.blog/2021/03/30/deploying-hp-bios-updates-a-real-world-example/)[@SMSagentTrevor]
- [Enable Product in win32_baseboard for Hardware Inventory](https://www.recastsoftware.com/resources/enable-product-in-win32-baseboard-for-hardware-inventory/) [Recast Blog]

### Dell

- [Dell BIOS Password Management – WMI](https://www.configjon.com/dell-bios-password-management-wmi/) [2020.09.11 @ConfigJon]
- [Dell Command Update - Task Sequence](https://garytown.com/dell-command-update-via-task-sequence) [@gwblok]
- [Set Dell BIOS settings through Intune and PowerShell](http://www.systanddeploy.com/2019/10/set-dell-bios-settings-through-intune.html) [@syst_and_deploy]
- [Dell 64-bit Flash BIOS Utility](https://miketerrill.net/2017/01/31/first-look-dell-64-bit-flash-bios-utility/) [@MikeTerrill]
- [How to Deploy Dell Command | PowerShell Provider with ConfigMgr](https://miketerrill.net/2016/10/23/how-to-deploy-dell-command-powershell-provider-with-configmgr/) [@MikeTerrill]

### Microsoft Surface

### Multi-Vendor Posts | Tools

- [Driver Automation Tool](https://msendpointmgr.com/driver-automation-tool/) [@modaly_it]
- [BIOS Management – Example Task Sequences (Dell | Lenovo | HP)](https://www.configjon.com/bios-management-example-task-sequences/) [@ConfigJon]
- [Firmware Management - GitHub](https://github.com/ConfigJon/Firmware-Management) [@ConfigJon]
- Configure WoL with ConfigMgr [Part 1](https://miketerrill.net/2020/04/21/configuring-wol-with-configuration-manager-part-1/) | [Part 2 (HP)](https://miketerrill.net/2020/04/21/configuring-wol-with-cm-for-hp-desktops-part-2/) | [Part 3 (Dell)](https://miketerrill.net/2020/04/28/configuring-wol-with-cm-for-dell-desktops-part-3/) [@MikeTerrill]
- [Links to Vendor Model and Driver Catalogs](https://www.deploymentresearch.com/links-to-vendor-model-and-driver-catalogs/) [@jarwidmark]

## Command Line | PowerShell Snips

### Lenovo

``` PowerShell
# Product Information - Model Identifiers
PS C:\> (Get-CimInstance -ClassName Win32_ComputerSystemProduct).Version
ThinkCentre M710q

PS C:\>(Get-CimInstance -ClassName Win32_ComputerSystemProduct).Name
10MQS0NE00

PS C:\>(Get-CimInstance -ClassName Win32_BIOS).SMBIOSBIOSVersion
M1AKT35A

```

### Dell

``` PowerShell
# Service Tag (Serial Number)
PS C:> (Get-WmiObject -class:win32_bios).SerialNumber
7YC9P2H

# SystemTypeID - Requires Dell Command Monitor Installed - Used in their DellSDPCCatalogPC.Cab (Enterprise Catalog)
PS C:> ((Get-CimInstance -Namespace root/DCIM/SYSMAN -ClassName DCIM_ComputerSystem).OtherIdentifyingInfo[2]).replace("DCIM:","")
1723

# SystemSKUNumber - Used in their CatalogIndexPC.cab
PS C:> (Get-CimInstance -ClassName Win32_ComputerSystem).SystemSKUNumber
06BB
```

### HP

``` PowerShell
# Product Code
PS C:\> (Get-CimInstance -Namespace root/cimv2 -ClassName Win32_BaseBoard).Product
8079
```

### Microsoft

### Generic

 ``` PowerShell OutPut
# Manufacturer
PS C:\WINDOWS\system32> (Get-WmiObject -Class:Win32_ComputerSystem).Manufacturer
Microsoft Corporation

#Model
PS C:\WINDOWS\system32> (Get-WmiObject -Class:Win32_ComputerSystem).Model
Surface Book 2

#Serial Number
PS C:\WINDOWS\system32> (Get-WmiObject -class:win32_bios).SerialNumber
020832083957
 ```
### Finding the Models in your environment, SQL:

``` SQL
-- HP
SELECT CS.Manufacturer0, CS.Model0, Count(*) as 'Count',BB.Product0
FROM v_GS_COMPUTER_SYSTEM CS
JOIN v_FullCollectionMembership fcm on CS.ResourceID=fcm.ResourceID
LEFT JOIN v_GS_BASEBOARD BB on CS.ResourceID=BB.ResourceID
WHERE fcm.CollectionID='SMS00001'and CS.Manufacturer0  LIKE 'HP'
GROUP BY CS.Model0, CS.Manufacturer0, BB.Product0
ORDER BY Count DESC

-- LENOVO
SELECT CS.Manufacturer0 ,CS.Model0, Count(*) as 'Count',CSP.Version0
FROM v_GS_COMPUTER_SYSTEM CS
JOIN v_FullCollectionMembership fcm on CS.ResourceID=fcm.ResourceID
LEFT JOIN v_GS_COMPUTER_SYSTEM_PRODUCT CSP on CS.ResourceID=CSP.ResourceID
WHERE fcm.CollectionID='SMS00001'and CS.Manufacturer0  LIKE 'LENOVO'
GROUP BY CS.Model0, CS.Manufacturer0,CSP.Version0
ORDER BY Count DESC

-- Everthing Else
SELECT CS.Manufacturer0 ,CS.Model0, Count(*) as 'Count'
FROM v_GS_COMPUTER_SYSTEM CS
JOIN v_FullCollectionMembership fcm on CS.ResourceID=fcm.ResourceID
WHERE fcm.CollectionID='SMS00001' and CS.Manufacturer0  NOT LIKE 'HP' and CS.Manufacturer0  NOT LIKE 'LENOVO'
GROUP BY CS.Model0, CS.Manufacturer0
ORDER BY Count DESC
```

**About Recast Software**
1 in 3 organizations using Microsoft Configuration Manager rely on Right Click Tools to surface vulnerabilities and remediate quicker than ever before.  
[Download Free Tools](https://www.recastsoftware.com/?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs#formarea)  
[Request Pricing](https://www.recastsoftware.com/pricing?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs)
