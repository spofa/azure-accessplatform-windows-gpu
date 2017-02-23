# Deploy a Windows NV VM.
# **WIP** [Check releases](https://github.com/Azure/azure-accessplatform-windows-gpu/tags)
* [Prereqs](#prereqs)
* [Credits](#credits)
* [Deploy and Visualize](#deploy-and-visualize)
* [PCoIP with Teradici and NVIDIA GRID Management on Azure for M60 Visualizations](#pcoip-with-teradici-and-nvidia-grid-management-on-azure-for-m60-visualizations)
* [MSFT OSCC](#msft-oscc)
* [Reporting Bugs](#reporting-bugs)
* [Patches and pull requests](#patches-and-pull-requests)

#### Prereqs
**Obtain a Trial License For the Windows Graphics Agent from [here](http://connect.teradici.com/cas-trial) to put in the template parameter**

* NVIDIA GRID 4.1 (369.71) with Azure Driver (Defaulted) and working
* All software installers and sample data are in D:\ and system installers like Teradici, Azure NVIDIA GRID Driver installers are in D:\DownloadInstallers

#### Credits
* The NVIDIA GRID 4.1 (369.71) with "Azure" Driver silent install works with certificate force trust - Thanks to [Mathieu Rietman](https://github.com/MathieuRietman)'s [commit on fork for the -f option](https://github.com/MathieuRietman/azure-accessplatform-windows-gpu/commit/a6bc42bc6936a75200f4d968d31ae0de00fe4e97)
* Dynamic Disk Selection with take function is as per the [Azure quickstart template](https://github.com/Azure/azure-quickstart-templates/tree/master/201-vm-dynamic-data-disks-selection)

#### Deploy and Visualize
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-accessplatform-windows-gpu%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>
<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-accessplatform-windows-gpu%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

#### PCoIP with Teradici and NVIDIA GRID Management on Azure for M60 Visualizations
* PCoIP Client Download for Windows is [here](http://teradici.com/swclient-windows)
* For GRID server interfaces for GPU management, please view [the grid software management sdk user guide](https://tdcm16sg112leo8193ls102.blob.core.windows.net/tdcm16sg112leo8193ls102/367.43-369.17-grid-software-management-sdk-user-guide.pdf)
* nView needs to be enabled manually. [User Guide](http://www.nvidia.com/content/quadro/pdf/nView-user-guide.pdf)
* Collection of the user dumps for the NVIDIA Display Driver 369.71  from within the VM on Display Driver Crash if occurs.
 * Details are [here](http://nvidia.custhelp.com/app/answers/detail/a_id/3335/~/tdr-(timeout-detection-and-recovery)-and-collecting-dump-files) 
* PCoIP RC Agent Log Collection (2.7.0.3589 ) or (2.7.0.4060) from the Teradici System Tray (right click Teradici Icon on System Tray) and collect Agent Logs (from the pop-up).
 * PCoIP RC Agent 2.7.0.4060 uses Multiple PCoIP encoding and options are there during provisioning to use either (2.7.0.4060 or 2.7.0.3589). The logic is present in the Script extension.
* The PCOIP Agent Logs (v1.10.*) from the Office Client machine of the end-user from <code>C:\Users<user_name>\AppData\Local\Teradici\PCoIPClient\logs</code>

#### MSFT OSCC
This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

#### Reporting bugs

Please report bugs  by opening an issue in the [GitHub Issue Tracker](https://github.com/Azure/azure-accessplatform-windows-gpu/issues)

#### Patches and pull requests

Patches can be submitted as GitHub pull requests. If using GitHub please make sure your branch applies to the current master as a 'fast forward' merge (i.e. without creating a merge commit). Use the `git rebase` command to update your branch to the current master if necessary.


