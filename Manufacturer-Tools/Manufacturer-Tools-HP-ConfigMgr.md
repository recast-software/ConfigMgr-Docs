<img style="float: right;" src="https://docs.recastsoftware.com/media/Recast-Logo-Dark_Horizontal_nav.png"  alt="Image" height="43" width="150">

# Manufacturer Tools - HP - ConfigMgr or Intune

## **DRAFT**

There are several ways you can leverage these tools, and it's going to be completely different based on your environment and business requirements.  Perhaps you want all of the content coming from your distribution points, and tightly managed bandwidth, or perhaps you want all of the updates coming from Dell so you don't have to manage that.  In these posts, we're going to leverage the ability to go back Dell, and not create packages in CM with all of the content.

This will be broken into several sub pages, as I found it was too much content of a single post, and will separate the tools into more bite size chunks.

All acronyms you can find details about on the parent Manufacturer tools page.

Table of Contents:

- Using HP Tools with ConfigMgr or Intune
  - Automating Install of HPCMSL
  - Automating Update of BIOS
    - Using HPCMSL
    - Using HPIA
  - Managing BIOS Settings
    - Using HPCMSL
    - Using HPIA
    - Using Native WMI (PowerShell)

## Automating the Install of HPCMSL

In these examples, the scripts will be going directly to HP to download the software and update, which works great if you have high bandwidth or split tunnelling setup.  If you would like to deploy using on prem DPs, that too is possible, and allows you full control over the version you're deploying, you'll just have to pay more attention to updates as they come up.

There are 2 ways to install HPCMSL, using the softpaq.exe download and install method, or powershell Gallery.  If you'd like to use the PowerShell Gallery, I've uploaded the ConfigMgr CIs for a Baseline Deployment to [GitHub](https://github.com/gwblok/garytown/tree/master/hardware/HP/ConfigItems).  In my lab, I've setup a Baseline with those 3 CIs, and have them deployed to all HP Devices, along with some other CIs for BIOS setting management.  You can adapt those scripts into Proactive remediation for Intune and target those to a group of HP Devices.

## Automating Update of BIOS: HPCMSL

This is where you have lots of options, you can leverage baselines, script downloading and updating packages or applications for deployment of BIOS, use task sequences, proactive remediation in Intune.

Currently I leverage HPCMSL to update bios two different ways, one for a highly controlled method of having HPCMSL keep our CM BIOS Pre-Prod package always updated and notify us when it has been updated, which makes for easy reporting, then promotion to production once its been tested.  I also leverage HPCMSL in a Run-Script for on-demand updating of BIOS during trouble tickets.

HPCMSL has an entire [module dedicated to BIOS](https://developers.hp.com/hp-client-management/doc/bios-and-device), download, update, or configuration, it's all there.

If you are looking for the hands-off approach, you can leverage baselines in ConfigMgr or proactive remedation in Intune that will automatically do it all for you, and you never have to think about it again. The Process will run from the client, compare it's current BIOS to HP.com, then update if a newer version is found.  

### Update BIOS via Baseline in Full OS

Once you have HPCSML Installed, you can create all sorts of great CIs for your Baseline.  One such CI can monitor your BIOS Version, compare to HP and Update when downlevel.



### Update BIOS via built-in BIOS Self-Updater when connected to Network


[!NOTE] HPCMSL will ONLY update BIOS on UEFI systems and requires 64-bit PowerShell, you'll need to leverage HPIA for Legacy systems. [More info](https://developers.hp.com/hp-client-management/doc/Get%E2%80%90HPBiosUpdates)




## Run Scripts

### Update BIOS

**About Recast Software**
1 in 3 organizations using Microsoft Configuration Manager rely on Right Click Tools to surface vulnerabilities and remediate quicker than ever before.  
[Download Free Tools](https://www.recastsoftware.com/?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs#formarea)  
[Request Pricing](https://www.recastsoftware.com/pricing?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs)
