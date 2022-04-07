<img style="float: right;" src="https://www.recastsoftware.com/wp-content/uploads/2021/10/Recast-Logo-Dark_Horizontal.svg"  alt="Image" height="43" width="150">

# Collection Commander

Collection commander is another great project created and maintained by [Roger Zander](https://twitter.com/roger_zander) on [GitHub](https://github.com/rzander/cmcollctr)

Once you've integrated it into ConfigMgr with a Click of a button, it adds a right click menu for you to pull up machines from a collection. This provides you the ability to run PowerShell scripts on one, many or all of the machines from the Collection Commander UI.

Differences from using "Run Scripts" that is built into the console:

Run Scripts is triggered through CM, and is logged in CM, leveraging the CM Client running in the System Content.  Collection Commander runs under the same context that you launched the CM Console in.

Collection Commander also comes with many pre-created scripts, worth looking at for a learning experience.

## Download & Install

Downloading is quite simple on the [GitHub](https://github.com/rzander/cmcollctr) Page, choose Release, which will provide you the MSI, go ahead and download and install.  You'll see a CMCollCtr Heart Shaped Icon on the desktop

[![CM Collection Commander 01](media/cmcollctr01.png)](media/CMcollctr01.png)

Once you open the application, if you want to integrate it into CM, click the button.  Otherwise, you can manually add computer names for you to take actions on.
[![CM Collection Commander 05](media/cmcollctr05.png)](media/CMcollctr05.png)

## UI & Usage

The UI shows lots of information, and allows you to take actions by right clicking.

The easiest way to leverage this tool is once it's integrated, right click on a collection, and choose "Collection Commander" which launches the UI.
[![CM Collection Commander 04](media/cmcollctr04.png)](media/CMcollctr04.png)
[![CM Collection Commander 02](media/cmcollctr02.png)](media/CMcollctr02.png)
Once open, you can select and right click on devices giving you a context menu with several options.
[![CM Collection Commander 03](media/cmcollctr03.png)](media/CMcollctr03.png)

If you choose Run PowerShell Code, you get a tool to run PowerShell code, with many scripts pre-created and available.

[![CM Collection Commander 06](media/cmcollctr06.png)](media/CMcollctr06.png)
[![CM Collection Commander 07](media/cmcollctr07.png)](media/CMcollctr07.png)

You can add your own custom scripts too, just place them into the scripts folder: (C:\Program Files (x86)\Collection Commander\PSScripts)
[![CM Collection Commander 08](media/cmcollctr08.png)](media/CMcollctr08.png)

This is another nice tool to have in your Service Desk / Admin arsenal.

**About Recast Software**
1 in 3 organizations using Microsoft Configuration Manager rely on Right Click Tools to surface vulnerabilities and remediate quicker than ever before.  
[Download Free Tools](https://www.recastsoftware.com/?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs#formarea)  
[Request Pricing](https://www.recastsoftware.com/pricing?utm_source=cmdocs&utm_medium=referral&utm_campaign=cmdocs)
