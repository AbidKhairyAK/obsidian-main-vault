---
page-title: "Proton: wmp10 32 bit prefix: this version of windows media player can only be installed on a computer running windows xp (32bit) - Gaming - Level1Techs Forums"
url: https://forum.level1techs.com/t/proton-wmp10-32-bit-prefix-this-version-of-windows-media-player-can-only-be-installed-on-a-computer-running-windows-xp-32bit/154988
date: "2023-07-24 17:02:27"
---

> Hello everyone again. I am running Arch Linux, with Wine-tkg latest, and i am trying to modify a Steam game pfx , which needs to be 32 bit and needs to have wmp and codecs. Following the instructions uploaded by a user to protondb page leaves me stuck at this point, in which wmp refuses to install no matter what. I have tried it on Debian testing with wine staging, Arch with this custom wine, i had set winecfg to WinXP, but nada, nothing works. I can see on protondb that everyone made it work aside from me. I don’t know what more to do at this point.
> 
> Instructions:  
> Run game once, go to steamapps/compatdata/460120/pfx and delete everything IN the folder. Run this IN pfx folder: WINEARCH=win32 WINEPREFIX="/mnt/Seagate/SteamLibrary/steamapps/compatdata/460120/pfx/" winetricks devenum quartz wmp10 , make sure to install the codecs. Enable CpuMultithreading: WINEPREFIX="/mnt/Seagate/SteamLibrary/steamapps/compatdata/460120/pfx/" wine ./drive\_c/windows/regedit.exe ( add new KEY named " Direct3D " in HKCU\\Software\\Wine , and in there add DWORD named " csmt " with value " 0x1 " ). Create a folder named " syswow64 " with nothing in it in drive\_c/windows . Symlink all DLL in steamapps/common/Proton x.x/dist/lib/wine/dxvk/ , into the game folder /common/Megadimension Neptunia VII/ , required because Proton lacks proper 32bit support. Next run the game normally from Steam, it should install VC runtime and then run with working video/events and without lag.
