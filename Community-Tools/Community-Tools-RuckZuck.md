<img style="float: right;" src="https://www.recastsoftware.com/wp-content/uploads/2021/10/Recast-Logo-Dark_Horizontal.svg"  alt="Image" height="43" width="150">

# RuckZuck

## Overview

[RuckZuck](https://ruckzuck.tools/) is a package manager for Windows.

The website has a link to a Wiki, which I used to help explain the config file, and a forum to get help from other users.  

I'm going to be focusing on the integration of this tool with Configuration Manager.

Basically, RuckZuck reaches out to software vendors and downloads the installers and does silent installs with a simple command line.

## Demo

This Demo will be using the ConfigMgr integration component and using it to populate applications into ConfigMgr.

### Installation of RuckZuck

I closed the CM Console

I downloaded the RuckZuck for CM, and ran the installer:
[![RuckZuck 01](media/RuckZuck01.png)](media/RuckZuck01.png)

That is the ONLY dialog box you see, once you click install, you're done, it does what it needs to do and then pops up the Config File

[![RuckZuck 02](media/RuckZuck02.png)](media/RuckZuck02.png)

I update a few things for my environment.  Since this is my lab, and my lab is simple, I've installed the software on my Single Primary Server.

In my lab, this is what I changed, so you'd need to adust for your lab. If you use this in your production, you'll want to go over each setting and confirm / change values, as these are fine for a lab, but not recommended for production.

[![RuckZuck 03](media/RuckZuck03.png)](media/RuckZuck03.png)

### Adding apps to CM with RuckZuck

This is very simple as well, basically you're presented with a catalog, you pick what you want and click "go" basically...

[![RuckZuck 04](media/RuckZuck04.png)](media/RuckZuck04.png)  
Once I click on Install New Software, the next dialog opens with a list of categories of available applications:  
[![RuckZuck 05](media/RuckZuck05.png)](media/RuckZuck05.png)  
I decided to use the search feature, I have a need for WinMerge, lets see if it's here:  
[![RuckZuck 06](media/RuckZuck06.png)](media/RuckZuck06.png)
Sweet, it's here, lets go ahead and "Download files and create CM App."
[![RuckZuck 07](media/RuckZuck07.png)](media/RuckZuck07.png)  
A new Dialog box (as shown above) opens and gives you progress as it creates the app in CM, downloads the content, creates the collection and deployment.  Below shows the console with all of the apps I've used RuckZuck to add tonight:
[![RuckZuck 08](media/RuckZuck08.png)](media/RuckZuck08.png)  
It distributed the content and created the deployment:
[![RuckZuck 09](media/RuckZuck09.png)](media/RuckZuck09.png)

Lets look at the application:
[![RuckZuck 10](media/RuckZuck10.png)](media/RuckZuck10.png)
It populates a lot of the fields in General information, and also the Software Center tab, along with a nice icon.
[![RuckZuck 11](media/RuckZuck11.png)](media/RuckZuck11.png)
The Deployment Type is created for X64:  
[![RuckZuck 12](media/RuckZuck12.png)](media/RuckZuck12.png)
Here it shows that it used my content locations that I set in the config file:
[![RuckZuck 13](media/RuckZuck13.png)](media/RuckZuck13.png)
Then creates simple commands for install and uninstall:  
[![RuckZuck 14](media/RuckZuck14.png)](media/RuckZuck14.png)

Content:
[![RuckZuck 15](media/RuckZuck15.png)](media/RuckZuck15.png)

RuckZuck downloads the install, and creates two PowerShell files, one for install and one for uninstall.  

### Software Center - Endpoint Install Test

Most of the apps on the top row I just created with RuckZuck as I test this tool out:
[![RuckZuck 16](media/RuckZuck16.png)](media/RuckZuck16.png)

[![RuckZuck 17](media/RuckZuck17.png)](media/RuckZuck17.png)

[![RuckZuck 18](media/RuckZuck18.png)](media/RuckZuck18.png)

When I look at the log, it all looks normal.  You can see the AppDT (Install_X64) installed.

> [!TIP]
> When I create Applications, I always have a descriptive AppDT Name so when I look in this log I know exactly what was installing.  Instead of Install_X64, I would have done WinMerge_i_X64, that's just a tip to easily find things in the logs.

## Test Drive

Click on the image to open in YouTube:

[![RuckZuck 19](media/RuckZuck19.png)](https://www.youtube.com/watch?v=Qsm88osD6rY)

## Summary

This was very slick, so far the most easy way to get applications into CM.  There is another function that will update these apps when new versions come out, which I might have to look into in the future as new versions for these gets released.  I'll make sure I update this post with those results.

**About Recast Software**
1 in 3 organizations using Microsoft Configuration Manager rely on Right Click Tools to surface vulnerabilities and remediate quicker than ever before.  
[Download Free Tools](https://www.recastsoftware.com/?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs#formarea)  
[Request Pricing](https://www.recastsoftware.com/pricing?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs)
