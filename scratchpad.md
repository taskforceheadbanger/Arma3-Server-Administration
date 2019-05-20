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


## Server Setup + Mods

After you have installed all of this software, you are now ready to start up FASTv2 and follow the instructions to begin installing SteamCMD, Arma3Server.exe(and x64) as well as install mods directly within FASTv2 from the Workshop and setup the first Headless Clients. Follow the instructions on this page but *DO NOT LAUNCH THE SERVER WHEN FINISHED*. We will be making some modifications to improve the speed at which the Arma3Server can operate by using custom binaries, as well as other optimizations. <https://github.com/alec-hs/Flaxs-Arma-Server-Tool-2/wiki/Setup-&-Installation>

## Performance Enhancements
Now that you have finished that, lets remove the "frameratelimit" BIS placed on the server so you can maximize performance.
Simply put, you need to replace the .exe's for the server that Steam placed into the Server folder. I believe you configured that and know this if you followed Flax's instructions properly.
The fast way, my GoogleDrive: https://drive.google.com/drive/folders/1KOZXibMbXItpNbkgN2NSZHKaYxfFbwyn?usp=sharing

The lenghty way, Directly from the developer: https://steamcommunity.com/app/107410/discussions/0/527274088392991283/

## Headless Client Setup
This is where things get tricky, we need to make a parameter file for the Werthless Headless Module mod.
The best way for us to do this is for you to follow the original instructions from Werthless (SUCH A GOOD GUY) himself.

*Werthles Headless Kit Guide*
_By Wert_
>Complete, concise, headless client kit to set up up any mission and server for use with headless clients. Build HC missions entirely from the >editor, once WHK script files are copied to your mission folder. HCs control AI units instead of the server.
<http://steamcommunity.com/sharedfiles/filedetails/?id=459917508>

<iframe width="638" height="390" src="https://www.youtube.com/embed/15VK_kNOu6o" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

#### Indepth Scripting Explanation (IMPORTANT)

1.  How to add scripts to your multiplayer mission

a)
Create HC(s) in your mission.
-   Insert Unit->Game Logic->Virtual Entities->Headless Client
-   Give it a unique name
-   Set it as playable

b)
Add "init.sqf" and "WerthlesHeadless.sqf" from:
@Werthles Headless Kit\Mission Scripts
to the mission folder, usually:
Documents\Arma 3 - Other Profiles\<profile name here>\MPMissions\<mission name.map>

The parameters in "init.sqf" configure:
-   Repeat on/off
-   Repeat delay
-   Debug on/off
-   Balancing mode
-   Start delay
-   Sync delay

Use simple balancing with 1 HC or to ignore balancing.

c)
If WH may transfer AIs while they are waiting at trigger-synced waypoints, add a non-overlapping waypoint before it, and sync this to the same trigger. HC transfer causes a temporary desync.

d)
Re-save your mission as a multiplayer mission.
2. How to use the test mission
Move
@Werthles Headless Kit\Addons\HeadlessTest.Altis.pbo
into
Arma 3( Server)\MPMissions
or
subscribe here.
3. How to start a server and connect HCs

Copy:
Arma 3\@Werthles Headless Kit\My Headless Kit
Arma 3\@Werthles Headless Kit\steam_appid
and paste as:
Arma 3( Server)\My Headless Kit
Arma 3( Server)\steam_appid
on the machines you will use as HCs or servers.

Then choose your next step:
a) Set up LAN game
b) Set up dedicated server game

Headless clients cannot connect to game clients hosting internet games.

a) Set up LAN game

i)
Start Arma 3 and host a LAN multiplayer game, with the password:
arma
If you will run the HC on the same machine, go to iii), then enter:
connect="-connect=localhost";

ii)
Open:
Arma 3\@Werthles Headless Kit\Get LAN IP
then note the machine's IPv4 address.

iii)
On your HC machine, open this with a text editor:
Arma 3( server)\My Headless Kit\Headless Client\ArmA2OA.par

iv)
Put the IP from ii) after connect="-connect=
E.g.
connect="-connect=192.168.0.10";

v)
If you have Arma 3( Server) installed on C:\ in the default location, start the HC using the appropriate shortcut from:
Arma 3( Server)\My Headless Kit\Example Shortcuts

vi)
If not, create a shortcut to:
Arma 3( Server)\arma3server.exe

vii)
Right click it and select properties.

viii)
At the end of "Target", add a space, then paste:
"-par=@My Headless Kit\Headless Client\ArmA2OA.par"

ix)
Double click on the shortcut to run the HC.

x)
You can start more than one HC per machine, or repeat this process on multiple machines Your HCs should join HC slots on your server.

b) Set up dedicated server game

You will need various internal and external IP addresses for this. To get them, open the folder:
Arma 3( Server)\My Headless Kit\
on the appropriate machine and run either
Get My Internal IP
(IPv4) or
Get My External IP
to get its IPs.

i)
On the server machine, in notepad, open:
Arma 3( Server)\My Headless Kit\Server\WerthlesHeadless_config.cfg

ii)
Add the external IPs of all external HCs and the internal IPs for all internal HCs to the headlessClients line, e.g.:
headlessClients[]={"81.46.54.91","192.168.0.55","56.45.87.19"...};

iii)
On the HC machine, in notepad, open:
Arma 3( Server)\My Headless Kit\Headless Client\ArmA2OA.par

iv)
Put the server's IP in this file after connect="-connect=
E.g. if connecting the HC to the server via LAN:
connect="-connect=192.168.0.10";
E.g. if connecting the HC to the server via the internet:
connect="-connect=81.46.54.91";

v)
If you have Arma 3( Server) installed on C:\ in the default location, start the server/HC using the appropriate shortcut from:
Arma 3( Server)\My Headless Kit\Example Shortcuts

vi)
If not, create shortcuts to:
Arma 3( Server)\arma3server.exe
for a HC and for the server.

vii)
Right click it and select properties.

viii)
At the end of "Target", add a space, then paste:
"-par=@My Headless Kit\Headless Client\ArmA2OA.par"
for the HC shortcut and:
"-par=@My Headless Kit\Server\ArmA2OA.par"
for the dedicated server shortcut.

ix)
Double click on the shortcuts to run the HCs and server.

x)
You can start more than one HC per machine, or repeat this process on multiple machines Your HCs should join HC slots on your server.

Type this into Arma 3 chat to check this:
#login three
4. Other information

a) Opening Ports
To host an Arma 3 dedicated server, forwarded these ports to your computer (UDP):
2302, 2303, 3478, 4379, 4380, 27000 - 27050

Here is a good video of this.

b) Mods and Customisation
The files to alter are in:
Arma 3( Server)\My Headless Kit\Server
or
Arma 3( Server)\My Headless Kit\Headless

To launch your server/HC with mods, open the related:
Arma2OA.par
file and replace:
@Example mod 1
etc. with your mods' folder names, separating with a ;

Full details of other parameters:
<https://community.bistudio.com/wiki/Startup_Parameters_Config_File>
<https://community.bistudio.com/wiki/Arma_3_Startup_Parameters>
<https://community.bistudio.com/wiki/server.cfg>
<https://community.bistudio.com/wiki/basic.cfg>

c) Arma 3 Launcher
You can start HCs and servers with Arma 3 Launcher, however Arma 3 Server currently doesn't have this, and for HCs connecting via the internet, you would still need to alter .cfg files (possibly for LAN HCs too).

d) Compatibility
i)
Works alongside DAC, if set up as described by Monsoon.<www.armaholic.com>
Set a long enough WH start delay so DAC set up finishes first.
Enter DAC zone group numbers as:
(max total groups)/(No. of HCs).
DAC and WH scripts shouldn't affect each other. WH script will control editor/Zeus/other script created AIs, DAC will control DAC units only.
ii)
WH script changes AI unit locality. This could break some scripts where local commands are issued for units that are no longer local.
iii)
Compatible with UPSMON. Add a long enough start delay for UPSMON to set up first.

## FINALIZE
> Now that you have gone through the process in its entirety, launch the server by pressing the play button. When you do FASTv2 will copy the  launch string to your clip board (due to a bug and its a useful one). You can use the "-mod=" bit to fill the `My Headless Kit\Server\ArmA2OA.par` file's required line for mods. MAGIC. Rinse and Repeat when you change your mods or they will have a hard time with life, as will you.
> Thats It!

```

**NOW** *Go kick some ass* and _PLEASE_ invite me to a game, or send me the video. If you have suggestions, feel free to contact me.

```



## Scripting Mission Files For Peformance
The first rule is, don't. A mission made only with a Zeus operator will function so much better and smoother than a heavily scripted mission. However, I have a trick up my sleeve to share.
> C0M1NG S00N
> C0D3 T0 US3
> `@DIVEYEZ`
> `#1337`
## Are You A Pilot?
*Do you want a free head tracking software that functions like TrackIR?*
Contact me in private, I bought a software for this that is not being used. Lets make a deal without money. =)

## Click For A Little Special Something
<a href="sauce/the-secret.md">CLICK HERE</a>
