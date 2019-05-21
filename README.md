<img src="images/arma.png"></img>
# Arma3 Server Administration

> This repository is to help those who wish to have a modded Arma3 server with their existing hardware, today, within the next 2.5 hours.
> You will need to follow this guide, and grab some things before this is possible.

__ __

## The Rules To Have Quick Enjoyable Setup, Performance, and Gameplay

-   1) First, do not use the regular steam client on the machine you wish to use as the server. This will make you unable to play on your account, because the server will be logged in as your user and you will get rejected.

-   2) Start with a fresh machine with decent resources. i5+, 4096MB Ram+, 20Mbps+ (AT THE VERY LEAST), and an SSD is perferred but not required, you will need 30+ Gigs of space. If you plan to mod the server, you may also need to install those mods, and they can come with a large data storage price. We recommend a 1TB drive or a 512GB SSD.

-   3) You will need a mouse, keyboard, monitor, internet connection, and access to the machine. This is in no way shape or form a headless install. You need to have physical access to that machine and the router of the network it is on!

-   4) Take things slow when choosing mission files and mods, creating conflicts by installing everything at once, will result in a denial for help when something goes wrong. We cannot help you learn to use a computer, practice common sense.

-   5) Client Optomizations; **AVOID #6 DO NOT DO THAT IF YOU HAVE A DUAL BAY OR DISCREET GRAPHICS CARD**. For this reason, this is a tricky one, but thank fully 'kubas' on Steam made a guide, I am linking that for you here <https://steamcommunity.com/sharedfiles/filedetails/?id=1731305438> Mixed results reported but I personally tried it and noticed a signifigant gain in performance from the first second I was operating with his methods. THANK YOU GOOD SIR, SENDING TRAFFIC YOUR WAY.

__ __


## Requirements

-   1) A unused x86 or x64 computer meeting the previously states specs. (i5+, 4096MB Ram+, 20Mbps+ (AT THE VERY LEAST) We recommend a 1TB drive or a 512GB SSD)

-   2) A Valid Steam account with a purchased copy of Arma 3. (DLC NOT REQUIRED)

-   3) Access to the administrator accounts on the computer, and the router of the network the computer is on.

-   4) Patience. This stuff eats up a lot of our time in our lives. 2000+ once fully involved within the first 3 years. Whats wrong with us?!?!
__ __

## Software You Will Need

<https://www.microsoft.com/en-us/software-download/windows10>
Windows 10 is free to install. You just cant change desktop look and feel without having a license.

<https://processhacker.sourceforge.io/>
This is for making sure things are running smooth, as we all know task manger does not always suffice when dealing with Arma.

<https://desktop.github.com/>
This is to download the repositories of code, and tools being provided, slowly but surely.

<https://notepad-plus-plus.org/download/v7.7.html>
This is for editing text files when configuring more complex setups. Not required but highly recommended.

<https://github.com/alec-hs/Flaxs-Arma-Server-Tool-2> information <https://forums.bohemia.net/forums/topic/220433-fast2-arma-server-and-steam-workshop-tool/>
FASTv2 is the server manager software we will be using to make this setup as easy and effortless as possible.
-   DOWNLOAD LATEST VERSION <https://deploy.kestrelstudios.co.uk/updates/FAST2/FAST2-latest.zip>

<https://forums.bohemia.net/forums/topic/122207-pbo-manager/>
PBO Manager for unpacking and packing mission files and addons. This is for advanced enhancements like, removing bad code or just simply adding the ; to the lines the authors forgot to do themselves. This will prevent Arma from flooding itself with error messages constantly.

__ __
## Server Setup + Mods

After you have installed all of this software, you are now ready to start up FASTv2 and follow the instructions to begin installing SteamCMD, Arma3Server.exe(and x64) as well as install mods directly within FASTv2 from the Workshop and setup the first Headless Clients. Follow the instructions on this page but *DO NOT LAUNCH THE SERVER WHEN FINISHED*. We will be making some modifications to improve the speed at which the Arma3Server can operate by using custom binaries, as well as other optimizations. <https://github.com/alec-hs/Flaxs-Arma-Server-Tool-2/wiki/Setup-&-Installation>
__ __
## Performance Enhancements
Now that you have finished that, lets remove the "frameratelimit" BIS placed on the server so you can maximize performance.
Simply put, you need to replace the .exe's for the server that Steam placed into the Server folder. I believe you configured that and know this if you followed Flax's instructions properly.
The fast way, my GoogleDrive: <https://drive.google.com/drive/folders/1KOZXibMbXItpNbkgN2NSZHKaYxfFbwyn?usp=sharing>

The lenghty way, Directly from the developer: <https://steamcommunity.com/app/107410/discussions/0/527274088392991283/>

Share with your group....
!! Clientside Instructions <https://steamcommunity.com/sharedfiles/filedetails/?id=1731305438> !!
__ __
## Headless Client Setup
This is where things get tricky, we need to make a parameter file for the Werthless Headless Module mod.
The best way for us to do this is for you to follow the original instructions from Werthless (SUCH A GOOD GUY) himself.

*Werthles Headless Kit Guide*
__By Wert__
> Complete, concise, headless client kit to set up up any mission and server for use with headless clients. Build HC missions entirely from the >editor, once WHK script files are copied to your mission folder. HCs control AI units instead of the server.

<http://steamcommunity.com/sharedfiles/filedetails/?id=459917508>

<a href="docs/whm.md">Modding & Scripting Guide __Here__</a>

<https://www.youtube.com/embed/15VK_kNOu6o>

## PORT FORWARDING
<https://community.bistudio.com/wiki/Arma_3_Dedicated_Server#Port_Forwarding>
Forward the range, not the individual ports.

## FINALIZE
> Now that you have gone through the process in its entirety, launch the server by pressing the play button. When you do FASTv2 will copy the  launch string to your clip board (due to a bug and its a useful one). You can use the "-mod=" bit to fill the `My Headless Kit\Server\ArmA2OA.par` file's required line for mods. MAGIC. Rinse and Repeat when you change your mods or they will have a hard time with life, as will you.
> Thats It!

```

**NOW** *Go kick some ass* and _PLEASE_ invite me to a game, or send me the video. If you have suggestions, feel free to contact me.

```
__ __

## Scripting Mission Files For Peformance And Functionality
The first rule is, don't. A mission made only with a Zeus operator will function so much better and smoother than a heavily scripted mission. However, I have a trick up my sleeve to share.

The first thing you should learn how to do to make life as a server admin easier is develop the knowledge on how to use Mission File Layers in the Editor and Compositions. You will not need to repeat things over and over when making missions if you can do this. To get you started, you may take some of mine which are precious. <https://github.com/diveyez/DEVGRU/tree/master/stuff/DEVGRU_Compositions>

The second thing you should do as a server admin is make your server and its players into its own faction so you can use it as a part of the editor, and Zeus. This saves SO MUCH TIME. <a href="scripts/orbat-building/README.md">__ORBAT-Creator-Setup__</a>

As of right now, my scripts are too massive for this setup. I have one suggestion and a bit of script with it.
Learn to use the Wiki for writing your own code. Lots of mods are poorly written. But to get you started as a newfound admin of a brand new arma server... I left some things for you @ <a href="scripts/">Scripts</a>
__ __

> C0M1NG S00N:
> M0AR C0D3 T0 US3
> THE TOCC MOD IS STILL BEING DEVELOPED, PLEASE BE PATIENT.
> `@DIVEYEZ loves you`


__ __
