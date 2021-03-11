<img style="float: right;" src="https://docs.recastsoftware.com/media/Recast-Logo-Dark_Horizontal_nav.png"  alt="Image" height="43" width="150">

# ConfigMgr | SCCM | MEMCM Community Tools

Community tools are abundant and diverse.  Ranging from SSRS Reports to WIM modification to OSD Frontends, entire Lab kits and so much more.  There are just too many to keep track of.  We're going to list several that we have experience with and have found valuable.  Some we'll plan to create sub pages for and provide additional guides and demos, but many will just get a small description, hopefully enough to pique your curiosity and get you to continue to look into them if you too think you can find value with them.  

Everyone has a unique environment with different business requirements, so while it may be the perfect fit for some, it could be the wrong fit for others. That’s why you’ll often see variants of several similar ideas that are just different enough to best accommodate each special situation.

If you feel we have missed any tools, feel free to reach out to us (@recastsoftware) and we’ll do our best to keep this updated.

We here are Recast Software are proud supporters of the ConfigMgr Community, sponsoring user groups and great events like MMS. We also make a subset of [Right Click Tools available free to the community](https://www.recastsoftware.com/#formarea).

## [ConfigMgr Community Tools Webinars hosted by Community Contributors](https://www.recastsoftware.com/configmgr-community-tools-webinar-series)

- March 23: Update and Modify WIM Files for Windows Deployment Scenarios, by Donna Ryan
- March 24: : OneVinn Tools, by Johan Schrewelius & Jorgen Nilsson
- March 31: BIOS & Drivers Deployment, Setting Up Your CM Infrastructure, by Maurice Daly & Nickolaj Andersen:
- April 1: Cloud Imaging using ConfigMgr, and MDT and PowerShell Deployment, by Johan Arwidmark

## ConfigMgr Community Hub & GitHub

Before we go much more into this page, we wanted to call out the [Community Hub](https://docs.microsoft.com/en-us/mem/configmgr/core/servers/manage/community-hub).  While currently in it's infancy, we think a lot more items will be coming to the community hub.  Many have started to heavily leverage github for scripts and projects, and it won't be a huge leap to start publishing work to the community hub, making it easy for others to import.  Some of the tools below will always be standalone, but eventually some might be assimilated into the community hub, making collaboration even easier.

Along with the Community Hub integrated right into the CM Console, many folks have published their work to GitHub.  We've created a sub page called "Scripts" which contains a number of GitHub repos from active community members that are work poking around to see what you can "steal with pride".

## Categories

- ### **Windows Media Manipulation**

  - [OSD Builder](https://osdbuilder.osdeploy.com/) (PowerShell Command Line)
    - OSDBuilder is a PowerShell module to help you perform Offline Servicing to a Windows Operating System Image.
    - [OSDeploy.com](https://www.osdeploy.com/) has several more great tools, and should be checked out.
  - [WIMWitch](https://msendpointmgr.com/wim-witch/) (GUI)
    - WIM Witch is a utility that can be used to update and modify WIM (OSD) & Upgrade Packages (IPU) files for Windows deployment scenarios.
  - [Surface Deployment Accelerator](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115) (PowerShell Command Line)
    - Script-driven tool to create Windows images (WIM) for test or deployment that closely match the configuration of Bare Metal Recovery (BMR) images, minus certain preinstalled applications like Microsoft Office and the Surface UWP application.

- ### **Drivers & BIOS w/ ConfigMgr**

  - [Driver Automation Tool](https://msendpointmgr.com/driver-automation-tool/) ([Maurice Daly](https://twitter.com/modaly_it))
    - The Driver Automation Tool is a GUI developed in PowerShell which provides full automation of BIOS and driver downloads, extraction, packaging and distribution with Dell, HP, Lenovo & Microsoft client hardware.
    - [Automating Intune Enrolled Device Driver Updates](https://msendpointmgr.com/2017/12/04/modern-management-automating-intune-enrolled-device-driver-updates/) - A single PowerShell script to query the model it is running on, download driver pack.  This Post is a walk-through.
    - [Modern Driver Management](https://msendpointmgr.com/modern-driver-management/) - A framework which incorporates Driver Automation Tool and other processes to round out the deployment of Drivers to Devices.
  - [OSDDrivers](https://osddrivers.osdeploy.com/) ([David Segura](https://twitter.com/SeguraOSD))
    - A complete framework for managing drivers for MDT, CM, or any deployment tool. This is a PowerShell module that provides a lot of functions, and gives you the power to automate and create your own custom solution based on this framework.

- ### **Operating System Deployment w/ ConfigMgr**

  - Front Ends
    - [UI++](https://uiplusplus.configmgrftw.com/) (Jason Sandys)
      - Displays information to the interactive user, solicits input from the interactive user, and then performs actions based on that user’s input and selections including populating task sequence variables during Operating System Deployment.
    - [UI++ Variant](https://github.com/theznerd/GUIpp) (Nathan Ziehnert)
      - A WYSIWYG editor for UI++ (Currently in Alpha)
    - [OSD Frontend](https://msendpointmgr.com/configmgr-osd-frontend/) (MSEndPointMgr)
    - [MDTWebFrontEnd](https://github.com/MaikKoster/MDTWebFrontend) (Maik Koster)
    - [Windows 10 UEFI BitLocker Frontend](https://www.niallbrady.com/2016/05/17/introducing-the-windows-10-uefi-bitlocker-frontend-for-system-center-configuration-manager-current-branch/) ([Niall C. Brady](https://twitter.com/ncbrady))
  - Scripts
    - [Variable Gather](https://github.com/jonconwayuk/PowerShell_Gather) (Jonathan Conway)
    - [Several by Johan Schrewelius at Onvinn](https://onevinn.schrewelius.it/Scripts01.html) (Gather | Auto Distribute | Format Drives | Copy Logs | Wake On Lan | TPM PassTheHash | TS Vars Dump)
    - OSD Tattoo Scripts
      - [OSD Info](https://home.memftw.com/configmgr-osd-information-script/) (Jason Sandys | Registry & WMI)
      - [OSD & IPU Info](https://garytown.com/collect-osd-ipu-info-with-hardware-inventory)(Gary Blok | Registry & WMI)
      - [OSD Tattoo](https://ccmexec.com/2018/03/script-to-tattoo-the-client-registry-during-osd-ps-version/) (Jörgen Nilsson | Registry)
      - [OSD Tattoo](https://deploymentbunny.com/2016/12/02/osd-add-information-to-the-computer-during-osd-using-a-custom-tattoo-step/) (Mikael Nystrom | Registry & WMI)
    - [Task Sequence Environment & Progress UI Functions](https://github.com/sombrerosheep/TaskSequenceModule) (Noah Swanson)
  - Other OSD Tools
    - [ConfigMgr Task Sequence Monitor](https://smsagent.blog/tools/configmgr-task-sequence-monitor/) ([Trevor Jones](https://twitter.com/SMSagentTrevor))
      - Allows realtime monitoring of your OS Deployments via a nice GUI tool.
    - [TSBackground](https://onevinn.schrewelius.it/index.html) ([Johan Schrewelius](https://twitter.com/josch62))
      - State of the art replacement for BGInfo as background and status
generator during OS deployment with MS Endpoint manager.
This full feathered C# application also offers password protected debug mode and remote control.
    - [Task Sequence Splash Screen](https://smsagent.blog/2020/03/12/windows-10-splash-screen-issue-fixed-for-w10-1909-configmgr-task-sequence/) - Typically triggered during in place upgrade to hide the desktop and provide a "pretty" screen to keep the users informed of the process.

- ### **ConfigMgr Web Services**

  - [WebService for ConfigMgr](https://onevinn.schrewelius.it/Apps01.html) ([Johan Schrewelius](https://twitter.com/josch62))
    - Onevinn Web Services exposes methods for adding and removing computers from Collections and AD Groups, retrieving group memberships, reset PXE-flags and move computers between OU’s, and more.
  - [ConfigMgr WebService](https://msendpointmgr.com/configmgr-webservice/) ([Nickolaj Andersen](https://twitter.com/NickolajA))
    - The ConfigMgr WebService has been designed to extend the functionality of Operating System Deployment with Configuration Manager Current Branch. It contains methods for performing operations in Configuration Manager, Active Directory and Microsoft Deployment Toolkit.

- ### **ConfigMgr Reporting**

  - [DocumentConfigMgrCB](https://github.com/paulwetter/DocumentConfigMgrCB)  (Paul Wetter | Check out many other great scripts in his [GitHub](https://github.com/paulwetter/WettersSource))
    - The script will document your CM Environment, worth a test drive.
  - [Client Health Report](https://smsagent.blog/free-configmgr-reports/client-health-report/) ([Trevor Jones](https://twitter.com/SMSagentTrevor))
    - A Fully Featured SSRS Report you can import that surfaces a lot of useful data about your CM Client Devices
  - [ConfigMgr Deployment Reporter](https://smsagent.blog/tools/configmgr-deployment-reporter/) ([Trevor Jones](https://twitter.com/SMSagentTrevor))
    - Provides detailed information about the deployments in your environment.
  - [ConfigMgr Task Sequence - Steps to Excel](https://github.com/gwblok/garytown/tree/master/TaskSequenceSteps2Excel) (Gary Blok)
    - Feed the Script a Task Sequence Name and it spits out an Excel document with all of the steps and a ton of info about each step.  Slick way to document your TS, submit it with your change requests, etc.

- ### **Application Management**

  - [RockZuck](https://ruckzuck.tools/)
    - RuckZuck is a free Software Package Manager for Windows, designed to keep the Software on your System(s) up to date even if the Software was not installed with RuckZuck.
  - [Chocolatey](https://chocolatey.org/) "The Package Manager for Windows - Modern Software Automation"
  - [WinGet](https://docs.microsoft.com/en-us/windows/package-manager/winget/) (Microsoft)
    - The winget command line tool enables developers to discover, install, upgrade, remove and configure applications on Windows 10 computers. This tool is the client interface to the Windows Package Manager service.
  - [PatchMyPC Home](https://patchmypc.com/home-updater)
    - Home Updater is a free, easy-to-use program that keeps over 300 applications up-to-date on your computer. It is an easy way to update or install a large list of programs on to your computer.
  - [PowerShell App Deploy Toolkit](http://psappdeploytoolkit.com/)
    - PADT has helped to provide a better end user experience for ConfigMgr Deployments than the native deployment options avialble to you.
  - [PowerShell App Deployment Toolkit - GUI](https://www.oscc.be/sccm/configmgr/powershell/posh/intune/Powershell-App-deployment-toolkit-GUI/)
    - GUI for creating applications using the PowerShell App Deployment Toolkit, including creating Software ID Tags for easier License Management.
  
- ### **Patch Management**

  - [PatchMaster](https://github.com/RobUK101/PatchMaster) (Robert Marshall)
    - PatchMaster is designed to automate the creation and delivery of Microsoft Patches to an SCCM Hierarchy
  - [Create Software Update Groups Tool 1.0.0 console extension](https://msendpointmgr.com/2016/05/10/create-software-update-group-tool-console-extension-for-configmgr/) (Nickolaj Andersen)
    - quickly and easily create a Software Update Group containing Software Updates determined by a set of Products and Classifications within a specific time span.
  - [Software Maintenance Script: Making WSUS Suck Slightly Less](https://damgoodadmin.com/2018/10/17/latest-software-maintenance-script-making-wsus-suck-slightly-less/) (Bryan Dam)
    - Automating the maintenance of software updates in CM, from WSUS Cleanup to... well.. everything

- ### **ConfigMgr Infrastructure**

  - [ConfigMgr Prerequisites Tool](https://msendpointmgr.com/configmgr-prerequisites-tool/) (GUI | Nickolaj Andersen)
    - ConfigMgr Prerequisites Tool is designed to help administrators prepare their infrastructure and systems when about to install System Center Configuration Manager.  I personally use this one when I'm setting up lab servers, and you'll see me reference it frequently.
  - [Configuration Manager Client Health](https://www.andersrodland.com/configmgr-client-health/) (Anders Rødland)
    - It detects and fixes known errors in Windows and the Configuration Manager Client, and enforces required services to run and start as Automatic.
  - [Client Startup Script](https://home.memftw.com/configmgr-client-startup-script/) (Jason Sandys)
    - To check configuration settings and the state of services that the ConfigMgr client agent depends on for successful operation as well as install the client agent if it is not installed or functioning properly.
  - [SQL Server Maintenance Solution](https://ola.hallengren.com/downloads.html) (Ola Hallengren)
    - Pre-created scripts to get you setup with industry standards for: SQL Server Backup, Integrity Check, and Index and Statistics Maintenance.  This is a great set of scripts to implement as so many others have already done it and you can get help from the community quite easy.  Here is a great Blog post on setting it by Garth: [Blog Post](https://www.enhansoft.com/installation-guide-to-ola-hallengrens-sql-server-maintenance-solution/)
  - [Community Tools](https://2pintsoftware.com/downloads-library/) from 2PintSoftware to help implement and leverage Microsoft BranchCache technology
  - Veeam Backup & Replication [Community Edition](https://www.veeam.com/virtual-machine-backup-solution-free.html)
    - Use Community Edition to protect VMs, cloud instances, physical servers, workstations, laptops or unstructured file data. Protect your production environment, your remote worker endpoint devices, use it in your home lab or even for migrations at no cost.

- ### **ConfigMgr Hydration / Lab Kits**

  - [YouTube - Setup ConfigMgr Step by Step - PatchMyPC](https://youtu.be/amrg_mlFvuk)
  - [GitHub - Skatterbrainz - CMBuild](https://github.com/Skatterbrainz/CMBuild)
  - [Hydration Kit For Windows Server 2016 and ConfigMgr Current / Technical Preview Branch](https://deploymentresearch.com/hydration-kit-for-windows-server-2016-and-configmgr-current-technical-preview-branch/)
  - [Hydration Kit For Windows Server 2019, SQL Server 2017 and ConfigMgr Current Branch](https://deploymentresearch.com/hydration-kit-for-windows-server-2019-sql-server-2017-and-configmgr-current-branch/)
  - [GitHub - Automated Lab](https://github.com/AutomatedLab/AutomatedLab)
    - [Set up a Hyper-V home lab with the AutomatedLab PowerShell module](https://4sysops.com/archives/set-up-a-hyper-v-home-lab-with-the-automatedlab-powershell-module/)
    - [Build a ConfigrMgr lab with AutomatedLab - Adam Cook](https://sysmansquad.com/2020/06/15/build-a-configrmgr-lab-with-automatedlab/)

- ### **Service Desk / Admin Tools**

  - [Right Click Tools](https://www.recastsoftware.com/right-click-tools) ([Recast Software](https://twitter.com/RecastSoftware))
    - Recast Software provides a Community Version with many handy tools, I'm not going to cover it hear, if you're looking for more info, check out the link.
  - [Client Center](https://github.com/rzander/sccmclictr) ([Roger Zander](https://twitter.com/roger_zander))
    - The tool is designed for IT Professionals to troubleshoot ConfigMgr Agent related Issues. The Client Center for Configuration Manager provides a quick and easy overview of client settings, including running services and Agent settings in a good, easy to use user interface.

- ### **Misc ConfigMgr Tools**

  - [Registry to PowerShell Converter](https://reg2ps.azurewebsites.net/) ([Roger Zander](https://twitter.com/roger_zander))
    - Automatically change .reg Files into PowerShell code.
  - [Create ConfigMgr Configuration Items from Group Policy Object](https://docs.microsoft.com/en-us/archive/blogs/samroberts/create-configmgr-configuration-items-from-group-policy-object) (Sam Roberts)
    - This script uses both the Configuration Manager and Active Directory PowerShell modules to query for registry keys associated with Group Policies then create the Configuration Items for each of the registry values.
  - [Collection Commander](https://github.com/rzander/cmcollctr) ([Roger Zander](https://twitter.com/roger_zander))
    - Trigger PowerShell Scripts on a list of devices. [Recast Deeper Dive](https://docs.recastsoftware.com/ConfigMgr-Docs/Community-Tools/Community-Tools-Collection-Commander.html)
  - [Windows as a Service (WaaS) Task Sequence Set Download](https://garytown.com/waas-1909-ts-download)
    - This is a complete set of Task Sequences, Baselines, and Content to create an extensive WaaS Process.  Update the TS's for your environment and let it rip.
    - WaaS Theory and other tips can be found on their Blogs [MikeTerrill.net](https://miketerrill.net/2019/01/01/windows-as-a-service-in-the-enterprise-table-of-contents/) & [GARYTOWN.COM](https://garytown.com/waas)
  - [Windows as a Service](https://www.imab.dk/windows-as-a-service/) ([Martin Bengtsson](https://twitter.com/mwbengtsson))
  - [Toast Notification](https://www.imab.dk/windows-10-toast-notification-script/) ([Martin Bengtsson](https://twitter.com/mwbengtsson))
  - [Toast Notification](https://byteben.com/bb/deploy-service-announcement-toast-notifications-in-windows-10-with-memcm/) ([Ben Whitmore](https://twitter.com/byteben))
  - [Windows 10 Upgrade GUI – For ConfigMgr\SCCM](https://richmawdsleyblog.wordpress.com/2017/12/08/windows-10-upgrade-gui-for-configmgrsccm/) ([Rich Mawdsley](https://twitter.com/RichMawdsley1))
  - [Free Tools form 1e](https://www.1e.com/community/free-tools/#TSEnv2)
  - [WMIExplorer](https://github.com/vinaypamnani/wmie2/releases/tag/v2.0.0.2) ([Vinay Pamnani](https://twitter.com/vinay_pamnani))
  - [Windows Sysinternals](https://docs.microsoft.com/en-us/sysinternals/) ([Sysinternals](https://twitter.com/Sysinternals))

### Related Posts / Pages

- [Manufacturer Tools](https://docs.recastsoftware.com/ConfigMgr-Docs/Manufacturer-Tools.html)
  - Page with Tools, Scripts and information provided from both the vendors directly and the community to support their devices. Primary focus on Dell, Lenovo, HP & Surface devices.

<br>

**About Recast Software**
1 in 3 organizations using Microsoft Configuration Manager rely on Right Click Tools to surface vulnerabilities and remediate quicker than ever before.  
[Download Free Tools](https://www.recastsoftware.com/?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs#formarea)  
[Request Pricing](https://www.recastsoftware.com/pricing?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs)  
[ConfigMgr Community Series Webinars](https://www.recastsoftware.com/configmgr-community-tools-webinar-series)
