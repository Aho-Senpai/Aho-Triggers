<h1>README !</h1>
<h2> Instructions on Setting up and using the RaidBuff Repo </h2>
<h2> Table of Contents </h2>

- [Installation](#installation)
- [Setting Up](#setting-up)
  - [# Setting up from in-game](#-setting-up-from-in-game)
    - [REQUIRED](#required)
    - [Settings](#settings)
    - [Options](#options)
    - [UPDATE](#update)
- [FAQ & Troubleshoting](#faq--troubleshoting)
## Installation
In case you are wondering how to install this : 

> `Triggernometry` > Select the folder `Remote triggers`  

> In the TOP LEFT > `Add` > `Repository from list`  

> Select `Aho's Raid Buffs` > BOTTOM LEFT > `Add Selected`  

Congrats, you have it installed. Now, on to [Setting Up](#Setup)  
## Setting Up
### # Setting up from in-game
Q. Why would i want to do this ?  
A. This way, you make sure your repository stays up-to-date. And you will not need to re-copy to local everytime there's an update to the repo.  
#### REQUIRED
1. `/e RaidBuffsSettingsFirstTimeSetup`  
This setup all the needed variables and settings. You NEED to do this ONLY ONCE.  
This will also display some text in the TOP LEFT forner of your screen, as well as an image in the middle of your screen.  
#### Settings
1. `/e RaidBuffsPlacement:100-50`  
This allows you to move where the raid buffs will display on your screen. (Replace `100` with your desired X value, and `50` with your desired Y value.)  
1. `/e RaidBuffsSize:40-40`  
This will allow you to change the size of the raid buffs images.  
#### Options
All of the options bellow are TOGGLES!
1. `/e RaidBuffsKeep`  
This will allow you to keep the image of the raidbuffs after the cooldown is over, and seeing the "drift"
2. `/e RaidBuffsTTS`  
Fairly simple : do you want TTS callout when a raidbuff is going out?
3. `/e RaidBuffsDisable`  
Do you want the images to be disabled ? This is NOT recommended without TTS enabled (as it makes the whole repository pointless ...)
4. `/e RaidBuffsVertical`  
Do you want the raidbuffs to be displayed vertically instead of horizontally?  

#### UPDATE
1. `/e RaidBuffsSettingsUpdateLinks`  
This is only required to do if there is an update to the image links, or some raidbuffs got added. 

## FAQ & Troubleshoting

Q. "Doing the `/e RaidBuffs...` commands in-game doesn't do anything."  
A. 
- Check you do NOT have "Hide Chat Log (for privacy)" enabled. (ACT > Plugins > FFXIV Parsing Plugin)  
- The commands are CASE-SENSITIVE. Please either copy/paste them, or make sure you respect the case.  

Q. "Images don't show up"  
A. If there was a recent update of the repo, try doing the [Update](#update). If not, ping me or DM me on discord.