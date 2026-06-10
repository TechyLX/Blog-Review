# Running Steam Games on MetaComputing AI PC with Framework Laptop 13 (arm64 + FEX)

## Tutorial: Running Steam Games on arm64 with FEX
One of the biggest pain points of choosing a less mainstream architecture like arm64 is the scarcity of pre-compiled software packages. While Ubuntu's own official repositories work fine across all supported architectures, third-party software — especially commercial closed-source applications — may not offer arm64 builds. The Steam game client is a prime example: Valve does not currently provide an arm64 version, and the vast majority of games on the platform are similarly x86-only.
This tutorial walks you through using the FEX emulator to get Steam running on your Ubuntu arm64 device. For more about FEX, check out their [GitHub](https://github.com/FEX-Emu/FEX) and [Wiki](https://wiki.fex-emu.com/index.php/Main_Page).
<img width="1280" height="853" alt="image" src="https://github.com/user-attachments/assets/ea6535b3-7098-4471-940d-cccc0d47259f" />
<img width="1280" height="853" alt="image" src="https://github.com/user-attachments/assets/2b1197b3-1d17-4050-9eb7-50d4e090f6cd" />

## Installing FEX
1. First, install curl:
```
$ sudo apt install curl
```
2. Add the FEX official PPA and install fex-emu. The most convenient way is to run the one-click install script provided in the [fex-emu README](https://github.com/FEX-Emu/FEX/blob/main/Readme.md):
```
$ curl --silent https://raw.githubusercontent.com/FEX-Emu/FEX/main/Scripts/InstallFEX.py | python3
```
3. The demo machine here runs Ubuntu 25.04. Since the currently available Ubuntu RootFS is based on 24.04, the automatic installer may not enable it by default. The fix is simple — manually run FEXRootFSFetcher to download the 24.04 RootFS, which works fine on newer releases. See the terminal session below:
```
RootFS not found. Do you want to try and download one?
Response {y,yes,1} or {n,no,0}
1
RootFS list selection
Options:
        0: Cancel
        1: Fedora 43 (SquashFS)
        2: Fedora 40 (SquashFS)
        3: Fedora 38 (SquashFS)
        4: ArchLinux (SquashFS)
        5: Ubuntu 24.04 (SquashFS)
        6: Ubuntu 23.10 (SquashFS)
        7: Ubuntu 23.04 (SquashFS)
        8: Ubuntu 22.10 (SquashFS)
        9: Ubuntu 22.04 (SquashFS)
        10: Ubuntu 20.04 (SquashFS)

Response {1-10} or 0 to cancel
5

Selected Rootfs: Ubuntu 24.04 (SquashFS)
    URL: https://rootfs.fex-emu.gg/Ubuntu_24_04/2025-03-04/Ubuntu_24_04.sqsh
Are you sure that you want to download this image
Response {y,yes,1} or {n,no,0}
y
  ...
Do you wish to extract the squashfs file or use it as-is?
Options:
    0: Cancel
    1: Extract
    2: As-Is
Response {1-2} or 0 to cancel
1
  ...
Do you wish to set this RootFS as default?
Response {y,yes,1} or {n,no,0}
1
Ubuntu_24_04 set as default RootFS
FEX is now installed. Trying basic program run
Linux roma-MC-FML13V04-Board 6.6.89 #2601 SMP Jan  7 2026 22:24:30 x86_64 x86_64 x86_64 GNU/Linux
```
4. After installation, verify that FEX is working properly by running uname inside the emulated environment:
```
$ FEXBash 'uname -a' 
Linux roma-MC-FML13V04-Board 6.6.89 #2601 SMP Jan  7 2026 22:24:30 x86_64 x86_64 x86_64 GNU/Linux
```

## Installing Steam
- Steam can be installed from its official mirror. Note: the installer linked on the Steam download page pulls x86-specific dependencies and won't work on arm64. However, there's an architecture-independent build available on the official mirrors that you can download and install directly:
```
$ wcurl https://repo.steampowered.com/steam/archive/stable/steam-launcher_latest_all.deb
$ sudo apt install ./steam-launcher_latest_all.deb
```
- Once installed, launch the Steam client via FEXBash:
```
$ FEXBash steam
```
- To launch from the desktop shortcut, right-click the Steam icon and select "Allow Launching."
<img width="813" height="538" alt="image" src="https://github.com/user-attachments/assets/161010ac-c346-4753-874f-800a27e473d3" />

## Have Fun
- After completing the steps above, launching Steam via either the command line or the desktop icon will bring you to the login screen. Once logged in, you can browse the store, download games, and play as usual.
<img width="1280" height="853" alt="image" src="https://github.com/user-attachments/assets/942c22b1-c4c1-4dcd-9571-11154542fd69" />


- Keep in mind that x86 emulation adds some performance overhead, so you may experience slightly lower speeds compared to native execution, and some games may not work yet. However, based on real-world testing, most games run surprisingly well under FEX. The FEX Wiki maintains a comprehensive [game compatibility list](https://wiki.fex-emu.com/index.php/Category:Game_Type_Application) — check it out for more details.
<img width="1280" height="853" alt="image" src="https://github.com/user-attachments/assets/125abcaa-d702-4262-b095-f473d038fa97" />

## References
-  https://discourse.ubuntu.com/t/tutorial-running-steam-games-on-arm64-with-fex/70215
- https://discourse.ubuntu.com/t/canonical-s-steam-snap-is-now-stable-on-arm64/83664
