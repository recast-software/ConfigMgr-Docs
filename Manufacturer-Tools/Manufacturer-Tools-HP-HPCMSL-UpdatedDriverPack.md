<img style="float: right;" src="https://www.recastsoftware.com/wp-content/uploads/2021/10/Recast-Logo-Dark_Horizontal.svg"  alt="Image" height="43" width="150">

# Manufacturer Tools - HPCMSL - Create Updated Driver Packs for OSD

A feature with HPCMSL is the ability to create a new driver pack from the latest available driver downloads.  You provide the model's platform info (4 character code for each model), along with OS Version and OS Build, and it will download all of the latest drivers, extract the inf drivers (which all you to DISM into an offline OS), and builds a compressed driver pack.

This is quite handy, as the standard driver packs can be come quite stale, and are often seldomly updated.  In the modern deployment world, you're often needing more recent drivers to resolve vulnerabilities or stability issues. This new command allows you to keep your driver packs that you apply during OSD fresh.

**About Recast Software**
1 in 3 organizations using Microsoft Configuration Manager rely on Right Click Tools to surface vulnerabilities and remediate quicker than ever before.  
[Download Free Tools](https://www.recastsoftware.com/?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs#formarea)  
[Request Pricing](https://www.recastsoftware.com/pricing?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs)
