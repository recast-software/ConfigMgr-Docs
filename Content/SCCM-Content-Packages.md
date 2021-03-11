<img style="float: right;" src="https://docs.recastsoftware.com/media/Recast-Logo-Dark_Horizontal_nav.png"  alt="Image" height="43" width="150">

# Packages

## MS Docs

<https://docs.microsoft.com/en-us/mem/configmgr/apps/deploy-use/packages-and-programs>

Packages, once the only option for getting your items deployed, is now back seat to using the Application Model for deploying your applications.  However, packages are still essential to a well run ConfigMgr eco system. Over the past decade I've seen Packages become the new default for deploying drivers during OSD, IPU and to already deployed machines.  

But a package is more than just a "Container for Content", it also has a powerful "Program" Engine, that allows you to run command lines with admin rights (System Access) or as the logged on user.  You can have it hidden, or interactive.  

## Common Uses

- Programs can be simple ways to provide end users the ability to run specific tasks with administrator rights.
  - Say your users have a poorly written app the doesn't work properly without being an Admin, you can put a "Program" in the Software Center that just launches that application.
  - Perhaps you have a script that you need to run when a user is on VPN or needs to reset a task, you can make those available for self-service be software center.
  - A "Self-Service" Toolbox for Support Staff or even End Users.
  - I make WMIExplorer, ProcMon, and other Diag Tools available this way for Techs
- Package Contents to transfer Files from A to B
  - Primary Application of this is for use in a Task Sequence, when you need to get files to a device, but then have a step in the Task Sequence act on them.
    - Script Libraries
    - Driver Packages
    - Firmware Updates
    - [See Run Command Line Step](docs/ConfigMgr-Docs/TaskSequence/SCCM_TaskSequence_Step_RunCommandLine.md) for examples of Script Libraries, and Driver Packages
    - [See Download Package Content Step](docs/ConfigMgr-Docs/TaskSequence/SCCM_TaskSequence_Step_DownloadPackageContent.md)

## CCMCache

Packages are one of the easier things to work with in the CCMCache. However this is no way to do a mapping of the Package ID to a "Friendly" Package name without reaching out to the server to pull that information. Here is a function that connects to the ComObject, and pulls back information for Packages.

``` PowerShell
Function Get-CCMCachePackages {
$CMObject = New-Object -ComObject 'UIResource.UIResourceMgr'  
$CMCacheObjects = $CMObject.GetCacheInfo()
$CCMPackages = $CMCacheObjects.GetCacheElements() | Where-Object {$_.ContentId -notmatch "Content" -and $_.ContentId -notmatch "-"}
return $CCMPackages
}
```

``` Output
ContentId         : PS200004
ContentVersion    : 15
Location          : C:\WINDOWS\ccmcache\6
LastReferenceTime : 10/13/2020 2:08:21 AM
ReferenceCount    : 0
ContentSize       : 4227
CacheElementId    : {3A0A348A-7F92-410B-B7F1-D1995ABC724D}

ContentId         : PS20006A
ContentVersion    : 34
Location          : C:\WINDOWS\ccmcache\g
LastReferenceTime : 10/13/2020 7:13:32 PM
ReferenceCount    : 0
ContentSize       : 1710
CacheElementId    : {AAB0BD15-CB97-4272-9C61-BDA820FD4855}

ContentId         : PS200071
ContentVersion    : 6
Location          : C:\WINDOWS\ccmcache\h
LastReferenceTime : 10/13/2020 7:13:32 PM
ReferenceCount    : 0
ContentSize       : 94
CacheElementId    : {949EC370-2477-4E47-942F-B018F8A2277B}

ContentId         : PS2002A8
ContentVersion    : 34
Location          : C:\WINDOWS\ccmcache\i
LastReferenceTime : 10/13/2020 7:13:32 PM
ReferenceCount    : 0
ContentSize       : 4981814
CacheElementId    : {864D43E2-A8F7-402C-BB89-987953835C22}

ContentId         : PS200004
ContentVersion    : 16
Location          : C:\WINDOWS\ccmcache\x
LastReferenceTime : 11/5/2020 4:42:17 PM
ReferenceCount    : 0
ContentSize       : 4223
CacheElementId    : {1FD7A54D-4E96-4CD4-8B82-5C93DC3874AB}
```

You're presented with all packages currently in the CM Cache. In the output above, you can see the same package is listed twice, but you can see the content version is different.  You can start to fill up your cache pretty quick if your content items are large and you update the frequently. This is a reason you'd want to create a cache management configuration item to keep things clean.

Find Duplicate Packages in Cache

``` PowerShell
$CMObject = New-Object -ComObject 'UIResource.UIResourceMgr'
$CMCacheObjects = $CMObject.GetCacheInfo()
$DuplicatePackages = $CMCacheObjects.GetCacheElements() | Group-Object -Property ContentID | ? {$_.count -gt 1}
$DuplicatePackages.Group
```

``` Output
PS C:\WINDOWS\system32> $DuplicatePackages.Group


ContentId         : PS200004
ContentVersion    : 15
Location          : C:\WINDOWS\ccmcache\6
LastReferenceTime : 10/13/2020 2:08:21 AM
ReferenceCount    : 0
ContentSize       : 4227
CacheElementId    : {3A0A348A-7F92-410B-B7F1-D1995ABC724D}

ContentId         : PS200004
ContentVersion    : 16
Location          : C:\WINDOWS\ccmcache\x
LastReferenceTime : 11/5/2020 4:42:17 PM
ReferenceCount    : 0
ContentSize       : 4223
CacheElementId    : {1FD7A54D-4E96-4CD4-8B82-5C93DC3874AB}
```

That snip was taken from a larger script that shows contents of Cache and automatically removes duplicates.
Full Script on [GitHub](https://github.com/gwblok/garytown/blob/master/RunScripts/CCMCacheReport.ps1)

**About Recast Software**
1 in 3 organizations using Microsoft Configuration Manager rely on Right Click Tools to surface vulnerabilities and remediate quicker than ever before.  
[Download Free Tools](https://www.recastsoftware.com/?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs#formarea)  
[Request Pricing](https://www.recastsoftware.com/pricing?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs)
