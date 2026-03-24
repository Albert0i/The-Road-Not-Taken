### [The Road Not Taken](https://www.poetryfoundation.org/poems/44272/the-road-not-taken) <br />── A Quest for Desktop Replacements 

> "Slavery is the law of life, and it is the only law, for it must be
observed: there is no revolt possible, no way to escape it. Some are
born slaves, others become slaves, and still others are forced to
accept slavery. Our faint-hearted love of freedom – which, if we had
it, we would all reject, unable to get used to it – is proof of how
ingrained our slavery is."<br />
"A escravatura é a lei da vida, e não há outra lei, porque esta tem de cumprir-se, sem revolta possível nem refúgio que achar. Uns nascem escravos, outros tornam-se escravos, e a outros a escravidão é dada. O amor cobarde que todos temos à liberdade — que, se a tivéssemos, estranharíamos, por nova, repudiando-a — é o verdadeiro sinal do peso da nossa escravidão."<br />
── [The Book of Disquiet by Fernando Pessoa](https://dn720004.ca.archive.org/0/items/english-collections-1/Book%20of%20Disquiet%2C%20The%20-%20Fernando%20Pessoa.pdf)

> "In a world without walls and fences, who needs windows and gates?"── [Alain Ruellan](https://www.linkedin.com/posts/alain-ruellan-0b775018_in-a-world-without-walls-and-fences-who-activity-7118788566607908864-aYjh?trk=public_profile_share_view)

> "To be clear: Windows isn’t bad. I actually like it. But the direction of Windows 11 is."── [Builtbybel](https://github.com/builtbybel/Winslop)


#### Prologue 
The day when tools you use for decades no longer serve you but the corporation. The day when AI accompanies with you on treading every flagstones. I shudder in sweat as if I were naked... Alas! This is wrong, this is *ALL* wrong... 

![alt Dilbert](img/Dilbert.JPG)

As an inveterate writer, it is my responsibility to pen down whirlpool and turbulence of this year. This is not about uninstalling and installing software, this is about the change of rudder and rigging, the change of course of mind and life, which may incur frustration and ecstasy. 


#### I. The Ignition
In January of 2026, three Linux distros have been tested, which includes: 
- [Linux Mint](https://linuxmint.com/)
- [MX Linux](https://mxlinux.org/)
- [Zorin OS](https://zorin.com/os/)

The third one is chosen not because the first two are not good. It's a matter of sense and sensibility, not to do with functionality and logicality. 

> Zorin OS comes with all the essential apps you need out of the box, so you can get working right away. Discover thousands of powerful apps from the built-in [Software store](https://help.zorin.com/docs/apps-games/install-apps/#software-store). 

More apps can be found in: 
- [Alternatives to Windows Apps](https://help.zorin.com/docs/apps-games/alternatives-to-windows-apps/)
- [AlternativeTo.net](https://alternativeto.net/)

You can even run many Windows apps in Zorin OS with [Windows App Support](https://help.zorin.com/docs/apps-games/windows-app-support/).

- [Wine](https://www.winehq.org/)
- [Bottle](https://usebottles.com/)
- [WinBoat](https://www.winboat.app/)

IMHO, I won't *recommend* running a dual boot system or running Linux plus virtualization software such as [virtual Box](https://www.virtualbox.org/)! That would deviate from our goal. 


#### II. The Predicament of Windows 11
![alt windows 11](img/Desktop%20(2026-02-28).JPG)

![alt 24H2](img/win-24h2.JPG)

I have tried hard to inhibit it from updating but in vain... I found it *rotten to the heart*, the update behaviour is triggered automatically on event base *and* on time base. It is hard coded in kernel level, there is practically no way to stop it, let alone to remove it. 

![alt Windows-Update-Service](img/Windows-Update-Service.JPG)

Strategies I employ includes: 
1. Continuously checking and stoping `Windows Update Service`*manually*, which makes me almost delirious;
2. Turn off WIFI connection *completely*, which makes my computer almost a brick;
3. Use `Parental controls` on router to block internet connection if WIFI is accidentally left on.

Once the update is on its way, the `Shutdown` option becomes `Update and Shutdown` and you are trapped! The only way to escape is to open a `cmd` and type: 
```
shutdown -s -t 0
```

As soon as you run this command, Windows will begin shutting down right away — no countdown, no waiting period. It’s the fastest way to trigger a shutdown from the command line. But there is a catch... 

---
**Caveat from AI**

When you run a shutdown command like:  

```bash
shutdown -s -t 0
```  

Windows will indeed shut down immediately — but if there’s a **pending update**, things change a bit.  

**🔍 How Pending Updates Affect Shutdown**
- **Normal shutdown**: If no updates are pending, the system powers off right away.
- **Pending updates**: When Windows has already staged updates (downloaded and ready to install), the shutdown options in the Start menu change to **“Update and Shutdown”** or **“Update and Restart.”**
- **Command-line shutdown**: Using `shutdown -s -t 0` bypasses the Start menu, but if updates are already staged, Windows may still apply them during shutdown. *In other words, you can’t always escape — the OS treats shutdown as an opportunity to finish the update process*.
- **Force shutdown**: If you use `shutdown /s /f /t 0` (with `/f` to force-close apps), you can sometimes skip the update cycle, but this risks leaving updates half-applied, which can cause issues.

⚖️ **Bottom Line**
- The command works, but pending updates can *override* it.
- Windows *prioritizes* completing updates once they’re staged, so even command-line shutdowns may *trigger* them.
- The *only* way to truly avoid it is to pause or disable updates before they reach the “pending install” stage.

---

The next day, when you turn on the computer, the war continues like clockwork. Good luck! 

Without further ado, let's talk about the softwares, besides these bundled by **ASUS** and those pre-installed by **Microsoft**, which consumes more than 40G, Following is the list: 

|     | **Application** | **Cross-platform** | **Alternative** |
| --- | ----------- | ----------- | ----------- |
| 1 | [Avast Free AntiVIrus](https://www.avast.com/free-antivirus-download#pc) | no | no |
| 2 | [Desktop Restore](https://www.majorgeeks.com/files/details/desktop_restore.html) 1.7.2.083 | no | no |
| 3 | [EaseUS Todo Backup Free 2025](https://www.easeus.com/download/tbf-download.html?srsltid=AfmBOopjxoA-5S-s9NZHvRwlyVqlGJzmH-HHgeyzu8L7sf7iAfGGXsuM) | no | no |
| 4 | [FileZilla](https://filezilla-project.org/) 3.68.1 | yes | --- |
| 5 | [FreeFileSync](https://freefilesync.org/) | yes | --- |
| 6 | [Git](https://git-scm.com/) | yes | --- |
| 7 | [GnuWin32: Make](https://gnuwin32.sourceforge.net/packages/make.htm)-3.8.1 | yes | --- |
| 8 | [GnuWin32: sed](https://gnuwin32.sourceforge.net/packages/sed.htm)-4.2.1 | yes | --- |
| 9 | [Google Chrome](https://www.google.com/chrome/) | yes | --- |
| 10 | [HandBrake](https://handbrake.fr/) 1.8.2 | yes | --- |
| 11 | [iTunes](https://www.apple.com/itunes/) 12.10.11 | no | no |
| 12 | [MariaDB](https://mariadb.com/)  11.7.2 | yes | --- |
| 13 | [Microsoft Visual Studio Code](https://code.visualstudio.com/) | yes | --- |
| 14 | [MongoDB Compass](https://www.mongodb.com/products/tools/compass) | yes | --- |
| 15 | [Mozilla Thunderbird](https://www.thunderbird.net/en-US/) | yes | --- |
| 16| [Node.js](https://nodejs.org/en) | yes | --- |
| 17 | [Notepad++](https://notepad-plus-plus.org/downloads/) | no | yes |
| 18 | [NVM for Windows](https://www.nvmnode.com/) 1.2.2 | yes | --- |
| 19 | [Ollama](https://ollama.com/) 0.13.5 | yes | --- |
| 20 | [Open-Shell](https://open-shell.github.io/Open-Shell-Menu/) | no | no |
| 21 | [Pea](https://peazip.github.io/) 10.0.0 | yes | --- |
| 22 | [Putty](https://putty.org/index.html) release 0.81 | yes | --- |
| 23 | [RealVNC Viewer](https://www.realvnc.com/en/connect/download/viewer/) 7.12.1 | no | yes |
| 24 | [Redis](https://github.com/zkteco-home/redis-windows) 8.4.0 | yes | --- |
| 25 | [Redis Insight](https://redis.io/insight/) 2.70.1 | yes | --- |
| 26 | [TightVNC](https://www.tightvnc.com/download.php) | no | yes |
| 27 | [Transmission](https://transmissionbt.com/) | yes | --- |
| 28 | [VLC media player](https://www.videolan.org/vlc/) 4.0.6 | yes | --- |
| 29 | [WinSCP](https://winscp.net/eng/download.php) 6.3.5 | yes | --- |
| 30 | [百度網盤](https://pan.baidu.com/disk/main) | yes | --- |

Software occasionally used: 

|     | **Application** | **Cross-platform** | **Alternative** |
| --- | ----------- | ----------- | ----------- |
| 1 | [Microsoft Edge](https://www.microsoft.com/en-us/edge/download?form=MA13FJ) | yes | --- |
| 2 | [HeidiSQL](https://www.heidisql.com/) | yes | --- |
| 3 | [Paint](https://www.microsoft.com/en-us/windows/paint) | no | yes |
| 4 | [ConvertZ](https://www.azofreeware.com/2006/03/convertz-802.html) | no | no |
| 5 | [ASS2SRT](https://apps.microsoft.com/detail/9p6zjkkntck1?hl=en-US&gl=SA) | no | no |
| 6 | [薦片影視](https://www.jianpian15.com/#/home) | no | no |

My ASUS notebook was bought in late 2024. 

![alt expert-book-info](img/expert-book-info.jpeg)

Roam says that it is NOT eligible for Windows 12 due to deficiency of [NPU](https://en.wikipedia.org/wiki/Neural_processing_unit) so much the worse! 


#### III. Where Zorin OS shines
![alt zorin os 18](img/Screenshot%20from%202026-02-15%2019-44-08.png)

Chances are there exist some applications you can not do without, and so much the worse, there are no alternatives. 

1. [WineHQ](https://www.winehq.org/)
2. [Bottles - Run Windows Software on Linux](https://usebottles.com/)
3. [WinBoat](https://www.winboat.app/)

##### **Edge Case 1**:  Interesting tidbits
1. [ConvertZ](https://www.azofreeware.com/2006/03/convertz-802.html)
> 中文簡繁內碼轉換器 - ConvertZ，簡單易用而且功能強大的中文內碼轉換工具，支援 GBK、Big5、HZ、Shift-JIS、JIS、EUC-JP、Unicode Little Endian、Unicode Big Endian、及 UTF-8 編碼，讓您輕鬆的對純文字檔案、檔案/資料夾名稱、剪貼簿文字、及 MP3 ID3 標籤在上述編碼之間進行轉換。

2. [ASS2SRT](https://apps.microsoft.com/detail/9p6zjkkntck1?hl=en-US&gl=SA) 
> A small tool designed specifically for Windows users to convert between ASS subtitles and SRT subtitles requires the installation of the. NET Desktop Runtime to function properly. This APP is available for free trial for 7 days. After that, you will need to pay to

3. [WinMD5Free](https://www.winmd5.com/?rid=winmd5)
> WinMD5Free is a tiny and fast utility to compute MD5 hash value for files. It works with Microsoft Windows 98, 2000, XP, Vista, and Windows 7/8/10/11.

To begin with, open and create a `Windows XP` bottle like so: 
![alt bottles-Windows-XP](img/ZorinOS-bottles-Windows-XP.png)

Select `sys-wine-11.0` in `Runner` and `Windows XP` in `Windows Version` like so: 
![alt bottles-runner](img/ZorinOS-bottles-runner.png)

![alt bottles-compability](img/ZorinOS-bottles-compability.png)

Press `Analyse...` and browse to the .exe file and run the analyse. It shows details info of the .exe, then press `Add and Launch`. If it is working properly, you can add it to the library for easy access.

![alt bottles-library-2](img/ZorinOS-bottles-library-2.png)

![alt bottles-convertz](img/ZorinOS-bottles-convertz.png)

![alt bottles-ass2srt](img/ZorinOS-bottles-ass2srt.png)

![alt bottles-winmd5free](img/ZorinOS-bottles-winmd5free.png)

*Easy peasy, lemon squeezy.* (易過借火)

**Bonus**

[SubShifter - Online SRT Subtitle Resync Tool](https://subshifter.bitsnbites.eu/)
> These tools shift all the time stamps of a movie subtitle file. They can be used for synchronizing the subtitles to a movie when there is a slight offset between the two (this can be the case when the subtitles and the movie come from two different sources), or when there is a time scale difference (for instance if the movie and the subtitle file have different frame rates).

##### **Edge case 2**: [Garmin Express](https://www.garmin.com/en-US/software/express/windows/)
> Use Garmin Express to update maps and software, sync with Garmin Connect and register your device. This desktop software notifies you when updates are available and helps you install them.

**System Requirements**

- Windows 10 or newer, Microsoft .NET 4.7.2 (included)
- 1024 x 768 display, USB port and 1 GB RAM
- High-speed internet access (not for use with dial-up, mobile or satellite connections)
- May require up to 20 GB free disk space
- For users running Windows 8 or older, please [download version 7 of Garmin Express for Windows](https://download.garmin.com/omt/express/GarminExpressWin7.exe).
---

Following steps depicted in [WineHQ AppDB](https://appdb.winehq.org/objectManager.php?sClass=version&iId=40213) and use version [7.16.3](https://garmin-express.en.uptodown.com/windows/download/92818424), *not* the latest one from official website. I slightly modify the scripts, upgrade to [Wine](https://www.winehq.org/) 11: 
```
sudo apt update && sudo apt full-upgrade
sudo apt install zorin-windows-app-support

wine --version 
```

Install [winetricks](https://github.com/Winetricks/winetricks): 
```
sudo apt install winetricks
sudo winetricks --self-update
```

Prepare installation folder: 
```
mkdir garmin
cd garmin 

export WINEPREFIX=/home/alberto/garmin
env | grep WINE
```

Initialize Wine environment: 
```
wineboot -i
```
![alt winboot-i-error](img/winboot-i-error.png)

Install the `.NET Framework 4.7.2`: 
```
winetricks --force dotnet472
```

From `4`, `4.5`, `4.6.1`, `4.6.2` to `4.7.2`, version by version, answering screen by screen until you meet: 
![alt dotnet 4.7.2](img/dotnet4.7.2.png)

Finally, install GarminExpress by: 

```
wine ./"GarminExpress-7-16-3.exe"
```
![alt Garmin-Express-launch](img/Garmin-Express-launch.png)

Plug in your device and check mount status: 

![alt Garmin-Express-mount](img/Garmin-Express-mount.png)

Just let GarminExpress search your device: 

![alt Garmin-Express-search](img/Garmin-Express-search.png)

As you can see, my device is found. Press `Add Device`: 

![alt ZorinOS-garmin-main](img/ZorinOS-garmin-main.png)

Sign in online account by pressing `Sign In`:

![alt ZorinOS-garmin-connect](img/ZorinOS-garmin-connect.png)

Fill in `email` and `password`:

![alt ZorinOS-garmin-signin](img/ZorinOS-garmin-signin.png)

Much to my disapointment! I can't input anything into the two boxes neither by typing nor copy-and-paste... which leaves me with tremendous sorry and sadness... 

The `Garmin Express.desktop` short cut is like so: 
```
[Desktop Entry]
Name=Garmin Express
Exec=env "WINEPREFIX=/home/alberto/garmin" wine "C:\\\\Program Files (x86)\\\\Garmin\\\\Express\\\\express.exe" ""
Type=Application
StartupNotify=true
Icon=AEB1_express.0
StartupWMClass=express.exe
```

BTW, to execute express.exe using CLI like so: 
```
export WINEPREFIX=/home/alberto/garmin
wine "/home/alberto/garmin/drive_c/Program Files (x86)/Garmin/Express/express.exe"
```

In some case, this error may appear: 
> ["This application could not be started" error when running a .NET Framework application](https://learn.microsoft.com/en-us/dotnet/framework/install/application-not-started?version=v2.0.50727&processName=LegacyApplicationsUninstaller.exe&platform=0009&osver=5&isServer=0&shimver=4.0.30319.0)

The result is: I got stranded and have to use GarminExpress on Windows 10 for the time being... 

See also: 

- [Wine 11.0 review - How to run Windows apps in Linux tutorial - January 2026 - 628508fe](https://youtu.be/b6_zgHtlhUw)

##### **Edge Case 3**: [iTunes](https://www.apple.com/itunes/)
> The latest entertainment apps now come installed with the latest macOS. Upgrade today to get your favorite music, movies, TV shows, and podcasts. You can join Apple Music and stream — or download and play offline — millions of songs, ad‑free.

[iTunes 12 for Windows - Technical Specifications](https://support.apple.com/en-us/112029)

**Hardware**:

- PC with a 1GHz Intel or AMD processor with support for SSE2 and 512MB of RAM

- To play Standard Definition video from the iTunes Store, an Intel Pentium D or faster processor, 512MB of RAM, and a DirectX 9.0-compatible video card is required.

- To play 720p HD video, an iTunes LP, or iTunes Extras, a 2.0GHz Intel Core 2 Duo or faster processor, 1GB of RAM, and an Intel GMA X3000, ATI Radeon X1300, or NVIDIA GeForce 6150 or better is required.

- To play 1080p HD video, a 2.4GHz Intel Core 2 Duo or faster processor, 2GB of RAM, and an Intel GMA X4500HD; ATI Radeon HD 2400; NVIDIA GeForce 8300 GS or better is required.

- Screen resolution of 1024x768 or greater; 1280x800 or greater is required to play an iTunes LP or iTunes Extras

- 16-bit sound card and speakers

- Internet connection to use Apple Music, the iTunes Store, and iTunes Extras

- iTunes-compatible CD or DVD recorder to create audio CDs, MP3 CDs, or backup CDs or DVDs. Songs from the Apple Music catalog cannot be burned to a CD.

**Software**:

- Windows 7 or later

- 64-bit editions of Windows require the iTunes 64-bit installer

- 400MB of available disk space

- Some third-party visualizers may no longer be compatible with this version of iTunes. Please contact the developer for an updated visualizer that is compatible with iTunes 12.1 or later

- Apple Music, iTunes Store, and iTunes Match availability may vary by country

- Apple Music trial requires sign-up and is available for new subscribers only. Plan automatically renews after trialor later
---

First and foremost, WinBoat has nothing to do with Wine! IMHO, Wine works for older software and simpler program. Winboat is not specifically innovative but a clever composite of multiple mature techniques. It *integrate* your favourite Windows application with Linux, just *like* magic. Under the hook, it runs a full-fledged Windows virtual machine. 

As of this writing, WinBoat is still 0.9 beta. Download `winboat-0.9.0-amd64.deb` from [here](https://winboat.app/) and intall it. WinBoat has many prerequisite you have to install one by one. When you launch WinBoat, it will tell you which components you missed. 

Creating a virtual machine in WinBoat is similar to using Virtual Box: you have to choose which version of Windows, how many cores, RAM and disk dedicated to it. The great advantage is if you do not have the .iso on hand, WinBoat will download it from the internet. 

![alt winboar-error](img/ZorinOS-winboar-error.png)

This complains that `permission denied` in `docker-compose -d`. 

> When Docker and Docker Compose are installed via **Snap**, they run inside a sandbox with strict confinement rules. That sandbox prevents them from accessing certain directories in your home folder (like `~/.winboat/`) and from communicating properly with the Docker daemon socket. This is why you see **“permission denied”** errors when trying to run WinBoat.  

Follow this [guide](winboat.md) to remove and re-install Docker if you come across this error. I met this because of built-in **Software Manager** of Zorin OS to install Docker in the first place. 

After that, things go smooth... 

![alt winboat-welcome](img/ZorinOS-winboat-welcome.png)

![alt winboat-license-agreement](img/ZorinOS-winboat-license-agreement.png)

![alt winboat-pre-requsite](img/ZorinOS-winboat-pre-requsite.png)

![alt winboat-install-location](img/ZorinOS-winboat-install-location.png)

Click `Select ISO File` and browse to `tiny11_25H2_jffeb9.iso`.
![alt winboat-configure-windows](img/ZorinOS-winboat-configure-windows.png)

![alt winboat-user-configuration](img/ZorinOS-winboat-user-configuration.png)

![alt winboat-hardware-configuration](img/ZorinOS-winboat-hardware-configuration.png)

![alt winboat-home-folder-sharing](img/ZorinOS-winboat-home-folder-sharing.png)

![alt winboat-review](img/ZorinOS-winboat-review.png)

![alt winboat-installation-finish](img/ZorinOS-winboat-installation-finish.png)

![alt winboat-extracting-iso](img/ZorinOS-winboat-extracting-iso.png)

![alt winboat-installing-win11](img/ZorinOS-winboat-installing-win11.png)

![alt winboat-installation-finish](img/ZorinOS-winboat-installation-finish.png)

![alt winboat-win11-first-open](img/ZorinOS-winboat-win11-first-open.png)

Adjust to `4 Cores` and `16G memory`: 
![alt winboat-custom-windows](img/ZorinOS-winboat-custom-windows.png)

![alt winboat-apps](img/ZorinOS-winboat-apps.png)

![alt winboat-configuration](img/ZorinOS-winboat-configuration.png)

![alt ZorinOS-winboat-about](img/ZorinOS-winboat-about.png)

Unactivated: 
![alt winboat-windows11-pro](img/ZorinOS-winboat-windows11-pro.png)

After installation of GarminExpress, iTunes and [OpenShell](https://open-shell.github.io/Open-Shell-Menu/): 
![alt ZorinOS-winboat-tiny11](img/ZorinOS-winboat-tiny11.png)

![alt ZorinOS-winboat-docker](img/ZorinOS-winboat-docker.png)

**Pros**: 

100% compability. Anything can be run on a virtual machine runs on WinBoat, in theory. 

**Cons**: 

Still in beta, not rock solid. Multiple prerequisites and huge resource consumption, less performant. No GPU acceleration pass-through for the time being. 

**License Caveat**: 

1. It is illegal to use unactivated version of Windows;
2. Microsoft does allow install and use unactivated version of Windows for evaluation and temporary use but not for day-to-day long term use;
3. Use of unactivated version of Windows may incur lawsuit and punishment but not for home use. 

See also: 

- [Seamless Compatibility? The Truth behind WinBoat](https://youtu.be/ST-dteJZuI4)
- [The End of Dual Boot: Run Windows Inside Linux Like Magic!](https://youtu.be/QwFxoDCXlM8)
- [Tiny 11 25H2 (v11) - Too Fast to be true!](https://youtu.be/NOTurC9yw8c)

My observation is: 
- WinBoat only supports one version of Windows at a time; 
- No USB passthrough for the time being. 

The resource: 

1. [Download Tiny11 25H2 2311](https://www.techspot.com/downloads/7578-tiny11.html#dw_description)
2. [Download Windows 11](https://www.microsoft.com/en-in/software-download/windows11)
3. [Download Windows 10 ISO files, save a copy before end of support](https://www.windowslatest.com/2025/08/08/download-windows-10-iso-version-22h2-before-end-of-support/)
4. [iTunes 12.10.11 for Windows (Windows 64 bit)](https://support.apple.com/en-us/106372)

##### **Edge Case 3 (Cont.)**: [Virtual Box](https://www.virtualbox.org/wiki/Linux_Downloads)
As a developer, running a dual-boot system or linux with Virtualized Windows is a technical compromise, which is inconvenient for daily use. WinBoat makes you *feel* as if they were one, it trades resource for compability, is more ideal for temporary solution if one has deeply *rooted* Windows application. 

**To cut it short, both GarminExpress and iTunes depend on USB passthrough from the host system.**

To resume our experiment, install latest version `7.2.6` of Virtual Box and extension pack. Use `tiny11_25H2_jffeb9.iso` to setup Windows 11: 4 Cores, 8G RAM, 64G disk, NAT network and shared folder... 

![alt A-Few-Moments-Later](img/A-Few-Moments-Later.png)

Plug in your device, open a terminal and type `lsusb`: 

![alt ZorinOS-lsusb](img/ZorinOS-lsusb.png)

If the USB device is present, in the `Settings` of virtual machine, switch to `Expert` mode, add `USB Filter` which is not *strictly* necessary but would simplify subsequent operations. 

![alt virtualbox-add-usbfilter](img/ZorinOS-virtualbox-add-usbfilter.png)

In the virtual machine menu, check to see if it is connected to the Windows 11. Run iTunes on Windows 11, `Sign In` to your Apple Account and wait for a while... Sometimes you need to un-plug and plug the device several times until the device presents on iTunes. After that, you can proceed to backup your device: 

![alt virtualbox-itune-backup](img/ZorinOS-virtualbox-itune-backup.png)

This pretty much concludes our journey on running `.exe` files on Linux. The best part of Zorin OS is to have [Windows App Support](https://help.zorin.com/docs/apps-games/windows-app-support/), many stand-alone `.exe` file can be run without any problem. 

![alt ZorinOS-screenfetch](img/ZorinOS-screenfetch.png)


#### IV. The Feather of Chromebook
> Chromebook is a lightweight ChromeOS PCs are designed for speed, security, and cloud computing, and are typically affordable, have long battery life, and are easy to use. They come with built-in Google services (such as Gmail and Drive), support Android apps and Microsoft 365 web version, and are suitable for word processing and teaching. 

> Crostini is the official method for running Linux applications directly on ChromeOS, offering a secure, containerized Debian-based environment. It enables developers and users to install IDEs, editors, and terminal tools, which integrate seamlessly into the Launcher and share files with the host system. It is supported on most modern Chromebooks via the settings menu.

![alt Crostini-architecture](img/Crostini-architecture.png)

##### 1. [FAQ](https://www.chromium.org/chromium-os/developer-library/guides/containers/containers-and-vms/#faq) (TL/DR)

- **Can I run a VM inside the VM?**

Yes, on machines with kernels >= 4.19 nested virtualization is on by default. However, performance will be slow if you don't have at least 8GB of RAM. Currently, we don't have performance testing or guarantees for nested VMs.

- **Can I run a container inside the container?**

Yes! You'll probably need to install the relevant packages first for whatever container format you want to run.

- **Do I have to manage VM updates?**

Nope! The [Termina](https://chromium.googlesource.com/chromiumos/overlays/board-overlays/+/HEAD/project-termina/) [VM](https://en.wikipedia.org/wiki/Virtual_machine) is a [component](https://chromium.googlesource.com/chromium/src/+/lkgr/components/component_updater/README.md) that is updated automatically.

Keep in mind that the [VM](https://en.wikipedia.org/wiki/Virtual_machine) is separate from the container.

- **How do I check the Termina version?**

The [Termina](https://chromium.googlesource.com/chromiumos/overlays/board-overlays/+/HEAD/project-termina/) version is tied to the ChromeOS version and updated at the same time. ChromeOS's version can be seen at `chrome://version`, and will look something like `14324.72.0`.

- **Can I run Windows programs?**

Sure, give [WINE](https://www.winehq.org/) a try. Compatibility will largely depend on [WINE](https://www.winehq.org/) though, so please don't ask us for support.

- **Why run VMs? Aren't containers secure?**

While containers often isolate themselves (via Linux [namespaces](https://man7.org/linux/man-pages/man7/namespaces.7.html)), they do not isolate the kernel or similar system resources. That means it only takes a single bug in the kernel to fully exploit the system and steal your data.

That isn't good enough for ChromeOS, hence we put everything inside a [VM](https://en.wikipedia.org/wiki/Virtual_machine). Now you have to exploit [crosvm](https://crosvm.dev/book/) via its limited interactions with the guest, and [crosvm](https://crosvm.dev/book/) itself is heavily sandboxed.

- **Don't VMs slow everything down?**

It is certainly true that [VM](https://en.wikipedia.org/wiki/Virtual_machine)s add overhead when compared to running in only a container or directly in the system. However, in our tests, the overhead is negligible to the user experience, and well worth the strong gains in system security.

- **Why run containers inside the VM? Why not run programs directly in the VM?**

In order to keep [VM](https://en.wikipedia.org/wiki/Virtual_machine) startup times low, we need [Termina](https://chromium.googlesource.com/chromiumos/overlays/board-overlays/+/HEAD/project-termina/) to be as slim as possible. That means cutting out programs/files we don't need or are about.

We use [dm-verity](https://gitlab.com/cryptsetup/cryptsetup/wikis/DMVerity) which requires the [Termina](https://chromium.googlesource.com/chromiumos/overlays/board-overlays/+/HEAD/project-termina/) image be read-only for [Security](https://www.chromium.org/chromium-os/developer-library/guides/containers/containers-and-vms/#security), but it also means we can safely share it between [VM](https://en.wikipedia.org/wiki/Virtual_machine) instances.

Further, the versions of programs/libraries we ship are frequently newer than other distros (since we build off of [Gentoo](https://gentoo.org/)), and are compiled with extra security flags.

Allowing user modifications to the [VM](https://en.wikipedia.org/wiki/Virtual_machine) prevents a stateless image that always works and is otherwise immune from user mistakes and bugs in programs.

Altogether, it's difficult to support running arbitrary programs, and would result in a system lacking many desired properties outlined above. Forcing everything into a container produces a more robust solution, and allows users to freely experiment without worry.

Also, [we love turtles](https://en.wikipedia.org/wiki/Turtles_all_the_way_down).

- **Why the name Crostini?**

It's a play off [crouton](https://github.com/dnschneid/crouton) which is a project to easily create full Linux environments (including developer tools) for users who turned on developer mode. [Crostini](https://www.chromium.org/chromium-os/developer-library/guides/containers/containers-and-vms/#Crostini) aims to satisfy the majority of use cases covered by [crouton](https://github.com/dnschneid/crouton), and is a larger & tastier snack than a crouton, hence the name.

See Also: 

- [Set up Linux on your Chromebook](https://support.google.com/chromebook/answer/9145439)
- [Crostini developer guide](https://www.chromium.org/chromium-os/developer-library/guides/containers/crostini-developer-guide/)
- [Running Custom Containers Under ChromeOS](https://www.chromium.org/chromium-os/developer-library/guides/containers/containers-and-vms/)
- [Linux for Chromebooks: Secure Development (Google I/O ’19)](https://youtu.be/pRlh8LX4kQI)

---

⚖️ “**The Charm of Crostini**”<br />── by copilot

[Crostini](https://dictionary.cambridge.org/dictionary/english-chinese-traditional/crostini?q=Crostini) (singular: crostino) are small Italian appetizers made from thin slices of bread, toasted until crisp, and topped with a variety of flavorful ingredients. 

The word *crostini* means “little crusts,” reflecting their crunchy texture and bite‑sized form. Traditionally served as antipasto (a small amount of food eaten at the beginning of an Italian meal), they offer a versatile base for both savory and sweet toppings. Common choices include creamy cheeses like ricotta (a soft, white Italian cheese that does not have a strong taste) or goat cheese, cured meats (醃肉) such as prosciutto (Italian dried ham (= meat from the leg or shoulder of a pig) served in very thin slices) or salami (a large sausage made from meat and spices that has a strong taste and is usually eaten cold in slices), and vegetables ranging from roasted peppers to fresh tomatoes. Olive oil, pesto (a green sauce used in Italian cooking, especially on pasta), or tapenade (a food made by crushing and mixing olives, anchovies and capers into a thick smooth paste) often enhance the flavor. 

Crostini differ from bruschetta, which uses larger rustic bread slices rubbed with garlic and typically topped with tomato and basil. Elegant yet simple, crostini are ideal for parties, wine tastings, or light starters. Their colorful presentation makes them visually appealing, while their variety ensures something for every palate. In essence, crostini embody Italian tradition, balancing rustic origins with modern culinary creativity.  

---

🧭 “**Chromebook and WinBoat: Layered VM–Container Isolation for Security**”<br />── by copilot

Running containers inside virtual machines (VMs) is a layered approach that merges two distinct forms of isolation. 
- VMs provide **hardware-level** separation, enabling multiple operating systems to run securely on shared infrastructure. 
- Containers, in contrast, isolate applications at the **process level**, packaging dependencies for portability and rapid deployment. 

Together, they create a defense-in-depth model where the VM acts as the fortified shell and the container as the agile inscription within. 

This architecture offers several advantages. It enhances security by adding an extra boundary against exploits, supports diverse operating systems, and simplifies compliance in regulated environments. Enterprises benefit from compatibility with legacy applications, operational consistency with existing VM workflows, and the ability to snapshot or migrate entire workloads. *Cloud providers rely on this model to ensure multi-tenant safety, while developers use it to replicate production environments with precision*.  

However, the approach is not without drawbacks. Containers inside VMs introduce performance overhead, resource duplication, and slower startup times compared to bare-metal containers. Management complexity increases, as administrators must orchestrate both VM lifecycles and container deployments. Networking and storage also become more intricate, with nested layers adding latency and consuming disk space. *For lean environments, such as Crostini with strict disk constraints, the trade-off is stark: ritual completeness and fortified boundaries versus efficiency and simplicity*. Ultimately, the container-inside-VM model is a deliberate choice, balancing resilience and flexibility against resource costs.

Both **Chromebooks** and **WinBoat** embody the same layered philosophy of isolation: running containers inside virtual machines to enhance security. In the Chromebook world, Google’s **Crostini** framework places a *lightweight* Debian container inside a VM, ensuring that Linux applications remain separated from the core Chrome OS environment. This double boundary — VM at the *hardware level*, container at the *process level* — protects the host system while still granting users flexibility.  

Similarly, **WinBoat** employs [KVM](https://en.wikipedia.org/wiki/Kernel-based_Virtual_Machine) to host a Windows 11 VM, and within that VM, Windows containers run applications. This mirrors the Chromebook approach, using virtualization as the fortified outer casing and containerization as the agile inner inscription. *The result is defense in depth: even if a container were compromised, the VM boundary prevents direct access to the host*.  

In both cases, the design is deliberate rather than coincidental. The VM–container layering balances **security, compatibility, and manageability**, making it especially valuable in multi-tenant or regulated environments. Symbolically, it is the scroll within a scroll — a heavier artifact to carry, but one that offers resilience and trust.

![alt Chromebook-Winboat](img/Chromebook-Winboat.png)

##### 2. Install Linux
> 前所未見的最新 [ASUS Chromebook Flip C434](https://www.asus.com/tw/laptops/for-home/chromebook/asus-chromebook-flip-c434/)， 使可翻轉 Chromebook 設計邁向全新境界。 集時尚現代造型、精巧便攜及強大規格於一身，讓您無時無刻都能完成使命。 ASUS Chromebook Flip C434 配備全新的 NanoEdge 四邊窄邊框 14 吋顯示器，搭載超薄邊框和無與倫比的 87% 螢幕佔比，提供真正身歷其境的觀賞體驗，同時獨家 360° ErgoLift 轉軸更能帶來極致工作舒適性。 而且 Google Play 商店1 還有各式各樣的應用程式等您親自探索。 只有最好才夠好，ASUS Chromebook Flip C434 就是最佳實例。

![alt chromebook-purchase-info](img/chromebook-purchase-info.jpeg)

To begin with, open `Settings` and search for `linux`, you should see `Linux development environment` section, just follow the on screen instructions: 
![alt setup-linux-dev-env-1](img/setup-linux-dev-env-1.png)

![alt setup-linux-dev-env-2](img/setup-linux-dev-env-2.png)

![alt setup-linux-dev-env-3](img/setup-linux-dev-env-3.png)

![alt setup-linux-dev-env-4](img/setup-linux-dev-env-4.png)

![alt setup-linux-dev-env-5](img/setup-linux-dev-env-5.png)

Due to *unknown* issue, you may come across error while installing Linux... Just press `Retry`. If error persists, reboot and try again. 
![alt setup-linux-dev-env-6](img/setup-linux-dev-env-6.png)

And finally: 
![alt penguin-debut](img/penguin-debut.png)

As you can see, around 1.44G is used. 
![alt penguin-debut-df](img/penguin-debut-df.png)

See also: 

- [Set up Linux on your Chromebook](https://support.google.com/chromebook/answer/9145439?b=rammus-signed-mp-v9keys&visit_id=639096762796065360-163165720&p=chromebook_linuxapps&rd=1)

Recommended to run first
```
sudo apt update && sudo apt upgrade -y

sudo apt install nano
sudo apt install fortune cowsay 
sudo apt install screenfetch

sudo apt install telnet
sudo apt install ftp
```

##### 3. Domestic
Create `~/.bash_aliases`: 
```
alias ll='ls -l'
alias la='ls -al'
alias l='ls -CF'
alias cls='clear'
alias ver='cat /etc/os-release'
alias edit='nano'
alias type='cat'
alias systeminfo='lshw'
alias ipconfig='ip a'
alias size='sudo du -h --max-depth=1'

alias pbcopy='xclip -selection clipboard'
alias pbpaste='xclip -selection clipboard -o'
```

Modify `~/.bashrc` by adding the following at the bottom: 
```
fortune | cowsay
```

Modify `~/.bash_logout` by adding the following at the bottom: 
```
echo
echo Goodbye $(whoami), have a nice day!
sleep 1
clear
```

[pbpaste && pbcopy for Ubuntu Linux 20.04](https://gist.github.com/diegopacheco/75de31680b3eaeb8824e994b81889f82)
```
sudo apt install xclip -y
```

Try out
```
pbcopy < /proc/cpuinfo 
pbpaste > tst.txt
cat tst.txt 
```

##### 4. [Docker](https://docs.docker.com/engine/install/debian/#install-using-the-repository)
a. Set up Docker's `apt` repository.
```
# Add Docker's official GPG key:
sudo apt update
sudo apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/debian
Suites: $(. /etc/os-release && echo "$VERSION_CODENAME")
Components: stable
Signed-By: /etc/apt/keyrings/docker.asc
EOF

sudo apt update
```

b. Install the Docker packages.

```
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo systemctl status docker

sudo usermod -aG docker $USER

docker --version 
docker-compose --version 
```

> Reboot the Linux container for the group changes to take effect. The easiest way is to type `sudo reboot` in the terminal or simply `restart` your Chromebook.

```
permission denied while trying to connect to the docker API at unix:///var/run/docker.sock
```

c. Verify that the installation is successful by running the `hello-world` image:
```
sudo docker run hello-world
```

d. Redis
```
docker run --name redis -d -p 6379:6379 redis:8.4.0

redis-cli 
```

e. MariaDB
```
docker run --name mariadb -d -p 3306:3306 -e MARIADB_ROOT_PASSWORD=123456 mariadb:11.7.2

mysql -h 127.0.0.1 -u root -p
```

##### 5. Database Clients
[Redis CLI](https://redis.io/docs/latest/develop/tools/cli/) and [MySQL CLI](https://dev.mysql.com/doc/refman/8.4/en/mysql.html)
```
sudo apt install default-mysql-client redis-tools
```

[RedisInsight](https://redis.io/downloads/?_gl=1*nx8art*_gcl_au*NDQzNjg2MjM4LjE3NjQ2MTY0NDE.#Redis_Insight)
```
sudo apt install Redis-Insight-linux-amd64.deb
```

[MongoDB Shell](https://www.mongodb.com/try/download/shell)
```
sudo apt install mongodb-mongosh_2.8.1_amd64.deb
```

[MongoDB Compass](https://www.mongodb.com/try/download/compass)
```
sudo apt install mongodb-compass_1.49.4_amd64.deb
```

[SQLite](https://sqlite.org/index.html)
```
sudo apt install sqlite3
```

[Turso CLI](https://github.com/tursodatabase/turso-cli)
```
curl -sSfL https://get.tur.so/install.sh | bash
```

[HeidiSQL](https://www.heidisql.com/download.php)
```
sudo apt install heidisql_12.16_amd64.deb
```

##### 6. Utilities
[jq](https://jqlang.org/) 
```
sudo apt install jq
```

[Pea](https://peazip.github.io/peazip-linux.html)
```
sudo apt install peazip_10.9.0.LINUX.Qt6-1_amd64.deb
```

[BaiduNetDisk](https://pan.baidu.com/disk/main#/index)
```
sudo apt install baidunetdisk_4.17.7_amd64.deb
```

[FileZilla](https://filezilla-project.org/download.php?type=client)
```
sudo apt install filezilla
```

[Transmission](https://transmissionbt.com/download)
```
sudo apt install transmission-gtk
```

[mc](https://midnight-commander.org/)
```
sudo apt install mc
```

[vlc](https://www.videolan.org/)
```
sudo apt install vlc
```

[kolourpaint](https://apps.kde.org/kolourpaint/)
```
sudo apt install kolourpaint
```

[tigervnc-viewer](https://tigervnc.org/)
```
sudo apt install tigervnc-viewer
```

[GNOME System Monitor](https://apps.gnome.org/SystemMonitor/)
```
sudo apt install gnome-system-monitor
```

[Microsoft Edge](https://www.microsoft.com/en-us/edge/download?form=MA13FJ)
```
sudo apt install microsoft-edge-stable_146.0.3856.72-1_amd64.deb
```

[Advanced REST client](https://github.com/advanced-rest-client/arc-electron/releases)
```
sudo apt install arc-linux-17.0.9-amd64.deb
```

[Text Editor](https://flathub.org/en/apps/org.gnome.TextEditor)
```
sudo apt install gedit
```

##### 7. [VSCode](https://code.visualstudio.com/Download) 
```
sudo apt install code_1.112.0-1773778351_amd64.deb
```

##### 8. [NVM](https://www.nvmnode.com/guide/download.html)
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash

nvm install 24.14.0

nvm --version 
node --version 

npm install -g nodemon
nodemon --version
```

##### 9. [Ollama](https://ollama.com/download) (Optional)
```
sudo apt get install zstd

curl -fsSL https://ollama.com/install.sh | sh

ollama --version 

ollama run gemma3:1b 
```

![alt chromebook-ollama](/img/chromebook-ollama.png)

To enable ollama API
```
systemctl status ollama
sudo systemctl edit ollama.service
```

Add the the following section
```
[Service]
Environment="OLLAMA_HOST=127.0.0.1:11434"
```

Restart ollama service
```
sudo systemctl restart ollama
```

Test ollama API on browser 
```
http://localhost:11434/api/tags
http://localhost:11434/api/ps
http://localhost:11434/api/version

https://docs.ollama.com/api/tags
```

##### 10. [libreOffice](https://www.libreoffice.org/) (Optional)
```
sudo apt install libreoffice
```

##### 11. [Crosh](https://www.chromium.org/chromium-os/developer-library/reference/device/crosh/) (Advanced)
Press `Ctrl + Alt + T` to open ChromeOS Developer Shell. You can run the `help` command to view a list of basic commands. Or run `help_advanced` for more advanced commands that are mainly used for debugging.

```
vmstat --help 

Usage:
 vmstat [options] [delay [count]]

Options:
 -a, --active           active/inactive memory
 -f, --forks            number of forks since boot
 -m, --slabs            slabinfo
 -n, --one-header       do not redisplay header
 -s, --stats            event counter statistics
 -d, --disk             disk statistics
 -D, --disk-sum         summarize disk statistics
 -p, --partition <dev>  partition specific statistics
 -S, --unit <char>      define display unit
 -w, --wide             wide output
 -t, --timestamp        show timestamp

 -h, --help     display this help and exit
 -V, --version  output version information and exit
```

```
vmc --help 
USAGE: vmc [
     start [--enable-gpu] [--enable-dgpu-passthrough] [--enable-big-gl] [--enable-virtgpu-native-context] [--vtpm-proxy] [--enable-audio-capture] [--extra-disk PATH] [--dlc ID] [--tools-dlc ID] [--kernel PATH] [--initrd PATH] [--rootfs PATH] [--vm-type <CROSTINI | ARC_VM | BOREALIS | BRUSCHETTA | BAGUETTE>] [--no-start-lxd] [--writable-rootfs] [--kernel-param PARAM]... [--oem-string STRING]... [--bios PATH] [--pflash PATH] [--bios-dlc ID] [--timeout PARAM] [--no-shell] [--user NAME] [--user-uid PARAM] [--user-group PARAM]... <vm name>

  |  stop <vm name>

  |  launch <main descriptor> [<descriptor>...]
  |  create [-p] [--size SIZE] --vm-type <vm type> <vm name> [<source media> [<removable storage name>]] [-- additional parameters]
  |  create-extra-disk --size SIZE <file name> [<removable storage name>]
  |  adjust <vm name> <operation> [additional parameters]
  |  destroy [-y] <vm name>
  |  disk-op-status <command UUID>
  |  export [-d] [-f] <vm name> <file name> [<removable storage name>]
  |  import [--vm-type <vm type>] <vm name> <file name> [<removable storage name>]
  |  inspect-backup <file name> [<removable storage name>]
  |  resize <vm name> <size>
  |  list
  |  logs <vm name>
  |  share <vm name> <path>
  |  unshare <vm name> <path>
  |  container <vm name> <container name> [ (<image server> <image alias>) | (<rootfs path> <metadata path>) ] [--privileged <true/false>] [--timeout PARAM]
  |  update-container-devices <vm name> <container name> (<vm device>:<enable/disable>)...
  |  usb-attach <vm name> <bus>:<device> [<container name>]
  |  usb-detach <vm name> <port>
  |  usb-list <vm name>
  |  key-attach <vm name> <hidraw path>
  |  pvm.send-problem-report [-n <vm name>] [-e <reporter's email>] <description of the problem>
  |  --help | -h
```

![alt vmc-list-Error-on-disk-VM-type-not-specified](img/vmc-list-Error-on-disk-VM-type-not-specified.png)

![alt vmc-stop-and-start](img/vmc-stop-and-start.png)

![alt vmc-start](img/vmc-start.png)

##### 12. Docker (Alternative)
> To install Docker on a Chromebook, you must use the built-in Linux development environment (Crostini) and follow the standard Docker Engine installation steps for Debian Linux. Docker Desktop for Linux may not run correctly in the Crostini environment.

**1. Update the apt package index and install necessary prerequisites**
```
sudo apt-get install apt-transport-https ca-certificates curl gnupg2 software-properties-common -y
```

**2. Add Docker's official GPG key**
```
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
```

**3. Set up the stable Docker repository for your architecture (usually amd64 or arm64, depending on your Chromebook's CPU)**:
```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
```

**4. Install the latest version of Docker Engine and containerd**
```
sudo apt-get install docker-ce docker-ce-cli containerd.io -y
```

**Add your user to the docker group to run Docker commands without sudo (this is highly recommended)**
```
sudo usermod -aG docker $USER
```

> Reboot the Linux container for the group changes to take effect. The easiest way is to type sudo reboot in the terminal or simply restart your Chromebook.

Test installation with 
```
docker run hello-world
```

Run Redis
```
docker run --name redis -d -p 6379:6379 redis:8.4.0

redis-cli 
```

Run MariaDB
```
docker run --name mariadb -d -p 3306:3306 -e MARIADB_ROOT_PASSWORD=123456 mariadb:11.7.2

mysql -h 127.0.0.1 -u root -p
```

In case you may need: 
```
sudo apt install default-mysql-client redis-tools
```

--- 

⚙️ **Software Management on Debian 12**<br />── by copilot

📖 Introduction
Debian 12 offers multiple ways to install and manage software: the traditional **APT package manager**, plus newer universal systems like **Flatpak** and **Snap**. Each has its own philosophy, strengths, and trade‑offs. Choosing the right one depends on what kind of software you want, how up‑to‑date you need it, and how much integration with Debian you prefer.

⚖️ **When to Use Each**

🔹 APT (Advanced Package Tool)
- **Best for**: Core system packages, libraries, and software officially maintained by Debian.  
- **Pros**: Stable, secure, tightly integrated with Debian.  
- **Cons**: Versions may lag behind upstream releases.  
- **Use case**: System tools (e.g., `gnome-system-monitor`, `vim`, `gcc`).

🔹 Flatpak
- **Best for**: Desktop GUI applications, especially those not in Debian repos or needing newer versions.  
- **Pros**: Sandboxed apps, access to Flathub (huge catalog), often more up‑to‑date.  
- **Cons**: Larger disk footprint, slower startup.  
- **Use case**: Modern apps like Notepad Next, Spotify, or newer LibreOffice.

🔹 Snap
- **Best for**: Cross‑platform apps distributed directly by developers.  
- **Pros**: Auto‑updates, wide catalog, easy installation.  
- **Cons**: Slower startup, heavier resource use, less native to Debian.  
- **Use case**: Apps like VS Code, Notepad Next, or proprietary software where Snap is the only option.

🛠 **How to Install Each Manager**

Install Flatpak
```bash
sudo apt update
sudo apt install flatpak -y
sudo apt install gnome-software-plugin-flatpak -y   # optional GUI integration
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

Install Snap
```bash
sudo apt update
sudo apt install snapd -y
sudo systemctl enable --now snapd.socket
```
*(Log out and back in to activate Snap fully.)*

APT is already installed
- Just use:
  ```bash
  sudo apt install <package-name>
  ```

✅ **Practical Guidance**
- **APT**: Use for system essentials and anything Debian provides.  
- **Flatpak**: Use for GUI apps you want in newer versions or not available in Debian.  
- **Snap**: Use if the developer only publishes a Snap, or if you want auto‑updates without relying on Flathub.  


![alt chromebook-screenfetch](img/chromebook-screenfetch.png)

![alt chromebook-desktop](img/chromebook-desktop.png)

![alt chromebook-linux-apps-1](img/chromebook-linux-apps-1.png)

![alt chromebook-linux-apps-2](img/chromebook-linux-apps-2.png)

![alt chromebook-lshw](img/chromebook-lshw.png)


#### V. The Touch of Vintage
I happen to have a [ASUS F8Vr](https://villman.com/Product-Detail/Asus_F8vr) notebook which is still in good condition. It was built in June 2008 and likely purchased in late 2008, with proof of use by spring 2009.

![alt F8Vr-date-manufactured](img/F8Vr-date-manufactured.jpeg)

It was pre-installed with [Windows Vista](https://en.wikipedia.org/wiki/Windows_Vista) Home Premium Edition, re-installed with [Windows XP](https://en.wikipedia.org/wiki/Windows_XP) Pro and was abandoned on 2014/2015 because of [Windows 10](https://en.wikipedia.org/wiki/Windows_10). It was certified and left untouched on garage and ready for [Electronic waste](https://en.wikipedia.org/wiki/Electronic_waste) until the spring of 2026. 

> Product Key: 38QFC-6C2MY-H3FDG-WKJ4T-GV9B8

> “Since the license remains valid, its practical purpose is to let you reinstall Windows Vista Home Premium on your notebook whenever you choose.”── by copilot

![alt F8Vr-spec-left](img/F8Vr-spec-left.jpeg)

![alt F8Vr-spec-right](img/F8Vr-spec-right.jpeg)

> **Product Description**<br />
Intel Core 2 Duo Processor P8400 2.26GHz, 3GB DDR2 Memory, 250GB HDD, ATI Radeon HD3470 256MB VGA, DL DVD+/-RW, 1.3MP Camera, 802.11a/b/g/N WiFi, Bluetooth, HDMI port, 8-in-1 Card Reader, Microsoft Windows Vista Home Premium

> **Revolutionary Infusion technology**<br />
With the staunch belief that good design enhances the consumer experience, ASUS launches the F8 notebook series with the revolutionary Infusion technology. An all round mobile computing workhorse based on the latest platform with advanced graphics solutions, the F8 is sophisticated inside-out with robustness, state-of-the-art computing technologies and unique aesthetics.

> 秉持著「優秀設計提升用戶體驗」的堅定信念，華碩推出搭載革命性Infusion技術的F8筆電系列。 F8是一款基於最新平台、配備先進圖形解決方案的全能型行動運算利器，從內到外都展現出精湛的工藝，兼具卓越的耐用性、尖端的計算技術和獨特的美學設計。(google translate)

The machine has [64 bits](https://www.productindetail.com/pn/asus-f8vr-4p014c) capability, which was weird, but fails to boot into Windows XP, which is not. 

##### Weekend project
![alt F8Vr-booting](img/F8Vr-booting.jpeg)

I use Zorin OS [Live USB](https://en.wikipedia.org/wiki/Live_USB) to have a full test of the machine, screen, keyboard, speaker, WIFI, Bluetooth, everything seems fine. 

Again, I happen to have a 1T SSD detached from a desktop computer and left in my drawer unattended. A whole weekend was spent to remove the disk, backup whatever the data and install the SSD. 

![alt F8Vr-back](img/F8Vr-back.jpeg)

![alt F8Vr-tray-with-mount](img/F8Vr-tray-with-mount.jpeg)

![alt F8Vr-tray-empty](img/F8Vr-tray-empty.jpeg)

![alt F8Vr-disk-old](img/F8Vr-disk-old.jpeg)

![altF8Vr-disk-new](img/F8Vr-disk-new.jpeg)

A 128G partition was created to make room for Zorin OS and everything seems fine. 

![alt F8Vr-first-screen](img/F8Vr-first-screen.jpeg)

A [wallpaper](img/thumb-1920-1158141.jpg) is *deliberately* chosen for reminiscence. 

![alt F8Vr-screenfetch](img/F8Vr-screenfetch.png)

##### GPU fix 
> Try to launch Brave browser with disabled hardware acceleration
```
brave-browser --disable-gpu
```

Turn off 
```
Settings > System > Use graphics acceleration when available  
```

![alt turnoff-graphic-acceleration](img/ZorinOS-turnoff-graphic-acceleration.jpg)

I manually added the `--disable-gpu` to every shortcut of [Brave Browser](https://brave.com/). 

See also: 

1. [Zorin OS 18 freezes/crashes when opening web browsers brave and chrome](https://forum.zorin.com/t/zorin-os-18-freezes-crashes-when-opening-web-browsers-brave-and-chrome/53065)

##### Swap fix 
> By default, Zorin OS creates a Swap File (usually 2gigs) not a Swap Partition.

As far as I can see, there is no swap file and whatsoever created in my machine... A 4G swap is manually added: 
```
sudo swapoff -a
sudo rm /swapfile

sudo touch /swapfile
sudo chmod 600 /swapfile
sudo fallocate -l 4G /swapfile

sudo mkswap /swapfile
sudo swapon /swapfile

swapon --show
```

To make the swap file permanent.
```
sudo nano /etc/fstab
```

Add the following line at the end of the file:
```
/swapfile none swap sw 0 0
```

See also: 

1. [Swap partition too small](https://forum.zorin.com/t/swap-partition-too-small/31730)
2. [Create or Resize Swap file/Partition](https://forum.zorin.com/t/create-or-resize-swap-file-partition/28878)


#### VI. Chinese input method on Zorin OS
Open **Software** and type `cangjie` to search, install `Cangjie`, `Cangjie Input Methods` and `Quick`: 
![alt install-input-method](img/install-input-method.png)

Open **Settings**, select `Region & Language`, press `Manage Installed Languages`: 
![alt manage-installed-languages](img/manage-installed-languages.png)

Press `Install/Remove Languages`: 
![alt installed-language-1](img/installed-language-1.png)

Select `Chinese (traditional)` and `English`: 
![alt installed-language-3](img/installed-language-3.png)

Open **Settings**, select `Keyboard`, press `Add Input Source`, add `Chinese (Cangjie5)` and `Chinese (Quick Classic)`: 
![alt add-input-source](img/add-input-source.png)

Use [Win]+[Space] to switch from English to Chinese. 

Click the **en** icon on taskbar: 
![alt input-method-1](img/F8Vr-input-method-1.png)

![alt input-method-2](img/F8Vr-input-method-2.png)

> “Hurrah for Karamazov!”<br />
─ Fyodor Dostoyevsky, The Brothers Karamazov


#### VII. Conclusion
To be honest, I am a big fan of Microsoft. My graduate project was a **RTF Editor**, a tool to edit and build Windows Help File, written in C++, compiled using Visual C++ 1.0, ran on Windows 3.1. 

![alt RTF-editor-main](img/RTF-editor-main.JPG)

![alt RTF-editor-about](img/RTF-editor-about.JPG)

Believe it or not, I still use [Windows XP](https://apk.tw/thread-695987-1-1.html) in my day‑to‑day life and in light of current juggling and future struggling, I quit... I mean Windows 11, 12... so on and so forth. 

> “When a relationship comes to an end, we have to clearly think whether to continue tolerating *or* simply to go away...Endings are not failures; they are transitions. Each one asks us to choose: do we carry the weight of what no longer serves us? or do we honor the experience and step forward lighter? To tolerate without purpose is to remain bound, to walk away with clarity is to redeem ourselves. In that choice lies our strength, and in that strength lies the beginning of something new.” ── by copilot


#### VIII. Bibliography 
1. [Switch Your Organization From Windows in 5 Steps](https://help.zorin.com/docs/getting-started/switch-your-organization-from-windows/)
2. [I Tried Every “Windows-Like” Linux Distro — Only ONE Truly Replaced Windows (Full Test)](https://youtu.be/ra7JNc9NEYs)
3. [Run Windows Apps on Linux (Wine Explained for Beginners)](https://youtu.be/gKKW3qZ-NZw)
4. [Winboat.app on Debian — Complete Installation Tutorial](https://youtu.be/Rqec-jmbQRs)
5. [Run Windows Apps on Linux Mint 22.3 with WinBoat (Full Beginner Guide)](https://youtu.be/PqpHaxATY3E)
6. [Windows Sucks. I'm Using DOS From Now On.](https://youtu.be/mwLIgdRj5bI)
7. [I Tried Zorin OS as a Windows 11 User (It Wasn’t What I Expected)](https://youtu.be/qe_epHU_opo)
8. [A Linux Distro Made For 99% of People](https://youtu.be/L5q36VojWk0)
9. [The Book of Disquiet by Fernando Pessoa](https://dn720004.ca.archive.org/0/items/english-collections-1/Book%20of%20Disquiet%2C%20The%20-%20Fernando%20Pessoa.pdf)


#### IX. Appendix from AI
Here’s the clear percentage breakdown, using the **Core 2 Duo** as the baseline at **100%**:

📊 **Relative Processing Power**

| Processor | Approx. PassMark Score | Relative to Core 2 Duo |
|-----------|-------------------------|------------------------|
| **Intel Core 2 Duo (2006)** | ~1,000–2,500 | **100%** |
| **Intel Atom N270 (2008)** | ~300 | **~15–25%** |
| **Intel Core m3‑8100Y (2018)** | ~3,000 | **~120–300%** |
| **Intel Core i5‑1335U (2022)** | ~17,000 | **~700–1,700%** |


#### Epilogue
```
The Road Not Taken
By Robert Frost

Two roads diverged in a yellow wood,    兩條路在黃葉林中分歧， 
And sorry I could not travel both.      可嘆我無法兩者都挑。
And be one traveler, long I stood       單身行路的我久久佇立，
And looked down one as far as I could   向其中一條極目望去，
To where it bent in the undergrowth;    直看到被林木掩住的轉角。
 
Then took the other, as just as fair,   然後我走了另一條路，一樣美麗，
And having perhaps the better claim,    而且還或許更加合宜，
Because it was grassy and wanted wear;  因爲它青草萋萋看似乏人問津；
Though as for that the passing there    雖説兩條路上行人來去，
Had worn them really about the same,    踩踏的程度其實相差無幾。
 
And both that morning equally lay       當天早上兩條路同樣被落葉覆蓋，
In leaves no step had trodden black.    沒有黑色的足跡沾染。
Oh, I kept the first for another day!   啊，頭一條路留待改日再來！

I shall be telling this with a sigh     很多很多年以後在某處，
Somewhere ages and ages hence:          我會嘆息著將此事提起：
Two roads diverged in a wood, and I—    森林中的路分岔成兩條，而我 –
I took the one less traveled by,        我選了較少人走的那條路，
And that has made all the difference.   於是再來的一切都迴然相異。

譯文: https://doctork.pixnet.net/blog/posts/11406125902
```


### EOF (2026/04/01)