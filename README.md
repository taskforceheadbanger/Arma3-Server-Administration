# Arma3 Server Administration

> This repository is to help those who wish to have a modded Arma3 server with their existing hardware, today, within the next 2.5 hours.
> You will need to follow this guide, and grab some things before this is possible.

## The Rules To Win Quick

1) First, do not use the regular steam client on the machine you wish to use as the server. This will make you unable to play on your account, because the server will be logged in as your user and you will get rejected.

2) Start with a fresh machine with decent resources. i5+, 4096MB Ram+, 20Mbps+ (AT THE VERY LEAST), and an SSD is perferred but not required, you will need 30+ Gigs of space. If you plan to mod the server, you may also need to install those mods, and they can come with a large data storage price. We recommend a 1TB drive or a 512GB SSD.

3) You will need a mouse, keyboard, monitor, internet connection, and access to the machine. This is in no way shape or form a headless install. You need to have physical access to that machine and the router of the network it is on!

4) Take things slow when choosing mission files and mods, creating conflicts by installing everything at once, will result in a denial for help when something goes wrong. We cannot help you learn to use a computer, practice common sense.

## Requirements

1) A unused x86 or x64 computer meeting the previously states specs. (i5+, 4096MB Ram+, 20Mbps+ (AT THE VERY LEAST) We recommend a 1TB drive or a 512GB SSD)
2) A Valid Steam account with a purchased copy of Arma 3. (DLC NOT REQUIRED)
3) Access to the administrator accounts on the computer, and the router of the network the computer is on.
4) Patience.

## Software You Need

https://www.microsoft.com/en-us/software-download/windows10
Windows 10 is free to install. You just cant change desktop look and feel without having a license.

https://processhacker.sourceforge.io/
This is for making sure things are running smooth, as we all know task manger does not always suffice when dealing with Arma.

https://desktop.github.com/
This is to download the repositories of code, and tools being provided, slowly but surely.

https://notepad-plus-plus.org/download/v7.7.html
This is for editing text files when configuring more complex setups. Not required but highly recommended.

https://github.com/alec-hs/Flaxs-Arma-Server-Tool-2 information https://forums.bohemia.net/forums/topic/220433-fast2-arma-server-and-steam-workshop-tool/
FASTv2 is the server manager software we will be using to make this setup as easy and effortless as possible.
-   DOWNLOAD LATEST VERSION https://deploy.kestrelstudios.co.uk/updates/FAST2/FAST2-latest.zip

https://drive.google.com/file/d/1uxP7Ed6nuu5IussVRIyQ-jBSpW8fFnIA/view?usp=sharing
PBO Manager for unpacking and packing mission files and addons. This is for advanced enhancements like, removing bad code or just simply adding the ; to the lines the authors forgot to do themselves. This will prevent Arma from flooding itself with error messages constantly.


## Server Setup + Mods

After you have installed all of this software, you are now ready to start up FASTv2 and follow the instructions to begin installing SteamCMD, Arma3Server.exe(and x64) as well as install mods directly within FASTv2 from the Workshop and setup the first Headless Clients. Follow the instructions on this page but *DO NOT LAUNCH THE SERVER WHEN FINISHED*. We will be making some modifications to improve the speed at which the Arma3Server can operate by using custom binaries, as well as other optimizations. https://github.com/alec-hs/Flaxs-Arma-Server-Tool-2/wiki/Setup-&-Installation

## Performance Enhancements
Now that you have finished that, lets remove the "frameratelimit" BIS placed on the server so you can maximize performance.
Simply put, you need to replace the .exe's for the server that Steam placed into the Server folder. I believe you configured that and know this if you followed Flax's instructions properly.
The fast way, my GoogleDrive: https://drive.google.com/drive/folders/1KOZXibMbXItpNbkgN2NSZHKaYxfFbwyn?usp=sharing

The lenghty way, Directly from the developer: https://steamcommunity.com/app/107410/discussions/0/527274088392991283/

## Headless Client Setup
This is where things get tricky, we need to make a parameter file for the Werthless Headless Module mod.






















## Scripting Mission Files For Peformance
The first rule is, don't. A mission made only with a Zeus operator will function so much better and smoother than a heavily scripted mission. However, I have a trick up my sleeve to share.
> COMING SOON
> CODE TO USE
> @DIVEYEZ



## Bonus Mod
When I started doing Arma again last year, an awesome set of gear appeared, then vanished. I present, the full Project Zenith: https://drive.google.com/file/d/1OICwIPUn3QawH8E2WvoYPzSszou89hxS/view?usp=sharing if you value your accounts, you will not post this to the Steam Workshop or any other sites. Share this privately as I just did not do with you ;)
I mean it, they will ban you, but _I NEVER WILL_. (_Retaliation for FallujahMedic's Actions, Eat Me @ BohemiaInteractiveSoftware_)
....................../´¯/)
....................,/¯../
.................../..../
............./´¯/'...'/´¯¯`·¸
........../'/.../..../......./¨¯\
........('(...´...´.... ¯~/'...')
.........\.................'...../
..........''...\.......... _.·´
............\..............(
..............\.............\...
#OPENSOURCEFTW
