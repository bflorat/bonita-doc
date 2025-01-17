# Bonita Studio installation

This page explains how to install Bonita Studio for developing processes. There are installer wizards for Windows, Linux, and Mac systems, and an OS-independent archive that can be installed on any system.

## Prerequisites

Check the [hardware and software requirements](hardware-and-software-requirements.md).

Before you download Bonita Studio, make sure that you know whether you are using a using a 32 or 64-bit system, and that you have the appropriate Java version installed:

* For Linux, to find out whether you are using a 32 or 64 bit Linux, run the following command: `getconf LONG_BIT`, which returns either 32 or 64.
* For Windows, see the [32 and 64 bit Windows FAQ](http://windows.microsoft.com/en-us/windows/32-bit-and-64-bit-windows).
* For Mac, 32-bit Java is no longer supported, so there is no 32-bit version of Bonita for Mac systems.

::: danger
Both Windows and Mac have default security settings that will prevent execution of Bonita. See below for further details about what you can do to bypass those security protections
:::

**Note for users of macOS 10.12.x and above** : There is an known issue on macOS Sierra and Java about the slowness of   java.net.InetAddress getLocalHost() which results in a slowness of the Bonita Studio (find more info on [thoeni](https://thoeni.io/post/macos-sierra-java/) or [plumbr](https://plumbr.eu/blog/java/macos-sierra-problems-with-java-net-inetaddress-getlocalhost)). To resolve this issue you shoud add your computer name to your /etc/hosts file : In a terminal, edit your `/etc/hosts` with sudo privilege, add your computer name to the local IP addresses `127.0.0.1 localhost <mycomputername.local>` and `::1 localhost <mycomputername.local>` (To find your macOS computer name, look at [Apple support dedicated page](https://support.apple.com/kb/PH25076)).

**Note for users of OS X 10.7.5 and above**: a new security feature called **Gatekeeper** prevents the installation of software that is not officially recognized by Apple.  
For more information and details of how to install Bonita Studio on a system running Gatekeeper, see the [Apple support site](https://support.apple.com/en-us/HT202491).

**Not for users of Windows 10**: the security feature called **SmartScreen** prevents execution of Bonita Studio installer.  When you get the "Windows protect your PC" pop up window, click on "More info" link and click on "Run anyway" button.

## Download Bonita Studio

For a Subscription edition of Bonita Studio, go to the [Customer Portal](https://customer.bonitasoft.com/download/request) and request a download.

For the Community edition of Bonita Studio, go to the Bonitasoft website [downloads page](http://www.bonitasoft.com/downloads-v2). On the download page you will get a download button based on your operating system auto-detection. If you want to download a different version (e.g. switch from 32 to 64-bit version), click on the **Customize you download** link.
On this page there are buttons to download the Studio installer for your current operating system and the _all in one_, OS-independent version.  
To download the installer for a different operating system, select it from the **Operating system** section.  
Then click the **_Download_** button.

When the download is complete, you have one of the following new files:

**Linux**  
Community edition  
- 32 bit: `BonitaStudioCommunity-x.y.z-x86.run`
- 64 bit: `BonitaStudioCommunity-x.y.z-x86_64.run`

Subscription editions   
- 32 bit: `BonitaSubscription-x.y.z-x86.run`
- 64 bit: `BonitaSubscription-x.y.z-x86_64.run`

**Windows**  
Community edition  
- 32 bit: `BonitaStudioCommunity-x..zy-x86.exe`
- 64 bit: `BonitaStudioCommunity-x.y.z-x86_64.exe`

Subscription editions  
- 32 bit: `BonitaSubscription-x..zy-x86.exe`
- 64 bit: `BonitaSubscription-x.y.z-x86_64.exe`

**Mac**  
Community edition  
- 32 bit: `Not provided`
- 64 bit: `BonitaStudioCommunity-x.y.z-x86_64.dmg`

Subscription editions  
- 32 bit: `Not provided`
- 64 bit: `BonitaSubscription-x.y.z-x86_64.dmg`

**Zip, no Installer (Windows or Linux)**
Community edition  
- `BonitaStudioCommunity-x.y.z.zip`

Subscription editions  
- `BonitaStudioSubscription-x.y.z.zip`

## Install using a wizard

To run the installer wizard for Linux, Windows, or Mac, double-click the downloaded file.

Then follow the installation wizard through to the end of the installation procedure.

For subscription editions: the installer import workspace feature applies only to local repositories.  
If you have shared repositories in your workspace, you will need to reconnect to these manually, and possibly migrate the processes to your new version of Bonita Studio.
The default workspace is automatically initialized at the end of the installation.

## Install using Zip archive (Windows or Linux)

To install Bonita Studio using the zip archive, unzip the downloaded .zip file to a folder on your hard drive. Avoid using a folder with a long path. Do not use a path that contains spaces.

## Start Bonita Studio

To start Bonita Studio, go to the directory where you installed it, and run the launcher for your operating system:

**Linux**   
Community edition  
- 32-bit: `BonitaStudioCommunity-linux`
- 64-bit: `BonitaStudioCommunity64-linux`

Subscription editions  
- 32-bit: `BonitaStudioSubscription-linux`
- 64-bit: `BonitaStudioSubscription64-linux`

**Windows**  
Community edition  
- 32-bit: `BonitaStudioCommunity.exe`
- 64-bit: `BonitaStudioCommunity64.exe`

Subscription editions  
- 32-bit: `BonitaStudioSubscription.exe`
- 64-bit: `BonitaStudioSubscription64.exe`

**Mac**   
Community edition  
- 32-bit: `Not provided`
- 64-bit: `BonitaStudioCommunity64.app`

Subscription editions  
- 32-bit: `Not provided`
- 64-bit: `BonitaStudioSubscription64.app`

## License

This information applies to the Subscription editions. No license is needed for the Community edition.

When you launch Bonita Studio for the first time, you need to install a license:

1. Click _**Copy to clipboard**_ to copy the request key from the pop-up
2. Use the generated request key to request a license on the [Customer portal](https://customer.bonitasoft.com/license/request)
3. _**Check**_ your email box (after a few minutes) and open the email from _no-reply@bonitasoft.com_
4. _**Download**_ the attached file (.lic)
5. Go back to your Bonita Studio, click _**Install license...**_, and select your .lic file.

<a id="enable_cache"/>

## Cache configuration

By default [cache](cache-configuration-and-policy.md) is disable for the web server embedded by Bonita studio, as it is more comfortable to realise development without cache.
But you can decide to activate cache, to be closer to the production display time. To do this, you need to follow those steps.

1. Close your Bonita Studio if he's up.
2. Go in the studio installation folder.
3. Open `BonitaStudioSubscription.ini` file if you use a **32-bits version** (`BonitaStudioSubscription64.ini` for a **64-bits**).
4. Change `-Dtomcat.extra.params=-DnoCacheCustomPage=true` to `-Dtomcat.extra.params=-DnoCacheCustomPage=false`.
5. Save file.
6. Start your Bonita studio. Now you have a cache for your living application and your custom page.



## Troubleshooting


#### Log files

In case of trouble when running Bonita Studio, you might want to take a look at log files.

Studio log file can be displayed from Bonita Studio in "Help" -\> "Show Bonita Studio log" menu.

If Studio fails to start, you can open the log file manually. File is named `.log` and is located in `<studio_folder>/workspace/.metadata` folder.   
Note that folder might be hidden and file might not be displayed if you choose to hide file extensions in your file manager.

#### OutOfMemory error in Bonita Studio

After installation, you might see an `OutOfMemory` error in Bonita Studio.
This error sometimes occurs when importing a large process definition.  
The log messages are similar to the following:

```log
!ENTRY org.bonitasoft.studio.importer 4 0 2014-04-25 09:43:49.467
!ERROR Import has failed for file Autorisation Engagement Depenses-2.0.bos

!ENTRY org.bonitasoft.studio.importer 4 0 2014-04-25 09:43:49.470
!ERROR
!STACK 0
java.lang.reflect.InvocationTargetException
Caused by: java.lang.OutOfMemoryError: GC overhead limit exceeded
```

To fix this issue, you need to increase the memory allocated to the JVM that runs Bonita Studio.

Edit the `*.ini` file that corresponds to the executable you use to launch the Studio (e.g. `BonitaStudioSubscription64.ini` if you run BonitaStudioSubscription64.exe) and modify this line: `-Xmx512m` to `-Xmx1024m` (or higher).

Then restart Bonita Studio.


#### Bonita Studio Welcome page stays blank on Linux (Ubuntu/Debian)

If the Welcome page displays fully white when you start-up your Bonita Studio:
<img src="bonita/images/${varVersion}/studio_welcome_page_ko.png" width="850px"/>

just install the missing packet libwebkitgtk by running the following command:
```shell
sudo apt-get install libwebkitgtk-1.0-0
```

Then the welcome page should display well, like this:
<img src="bonita/images/${varVersion}/studio_welcome_page_ok.png" width="850px"/>
