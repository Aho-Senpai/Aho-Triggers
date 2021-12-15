<h1>README !</h1>
<h2> Instructions on Setting up and using the RaidBuff Repo </h2>
<h2> Table of Contents </h2>

- [Installation](#installation)
- [Setting Up](#setting-up)
  - [Keeping Everything Remote](#keeping-everything-remote)
  - [Copy Settings Locally](#copy-settings-locally)
- [FAQ & Troubleshoting](#faq--troubleshoting)
## Installation
In case you are wondering how to install this : 

> `Triggernometry` > Select the folder `Remote triggers`  

> In the TOP LEFT > `Add` > `Repository from list`  

> Select `Aho's Raid Buffs` > BOTTOM LEFT > `Add Selected`  

Congrats, you have it installed. Now, on to [Setting Up](#Setup)  
//todo: add pictures, maybe
## Setting Up
Here, you have 2 options. you can either 
[Keep Everything Remote](#keeping-everything-remote) 
or, you can 
[Copy Settings Locally](#copy-settings-local).  
The first one is recommended.
### Keeping Everything Remote
Here, you have a few ways to do this. What i'd recommend you do :
(NOTE : you will only have to do this ONCE)
> IN GAME > `/e RaidBuffsSize` (we will change the size later if needed.)  

> IN GAME > `/e RaidBuffsPlacement`  

> TRIGGERNOMETRY > Select `# - Raid Buffs Placement` Trigger in the `Raid Buffs` Repo > TOP LEFT > `Edit trigger`  

> Make sure you have the FIRST ACTION selected > `Edit Action`  

> On the BOTTOM LEFT you will see a mouse icon with X/Y positions. Place your mouse where you want the <ins>top left</ins> of your RaidBuffs to be. Note them down. (the decimal values don't matter)  

IF you do not have `Developer mode` enabled : Triggernometry > TOP RIGHT > `Edit configuration` > `Miscellaneous` > Enable `Developer mode`. You can then close the Configuration window.  

> Triggernometry > TOP RIGHT > `View state` > `Table variables` > `Persistent` > `PermaRaidBuffTable` > `Edit variable`  

> Here, you can enter the values you want for your X/Y, as well as the size (square is recommended, but you can have different values for height/width if you desire. Quality is not guaranteed if you do so).  
Enter your desired values on the row below. (Aka : do not replace `XPosRaidBuffAura` for example.)  

> You will also NEED to fire the `# - Setup Table Permanant Variable : Image Links` trigger once.  
`Right Click` > `Fire`. That's all. Really

Congratulations, the hard part is done. Now, all that's left for you to do is enable the 4 optional settings if you want them.  
THOSE SETTINGS ARE TOGGLES ! 

Typing this IN GAME  
`/e RaidBuffsVertical` : Makes the Raidbuffs go from TOP TO BOTTOM instead of LEFT TO RIGHT. Do it again to revert  
`/e RaidBuffsTTS` : Enables TextToSpeech on Raid Buff use. this will callout all RaidBuffs comming from your party members  
`/e RaidBuffsKeep` : This will keep the Raid Buffs Images active after the cooldown is over, and will display a timer from that point onwards  
`/e RaidBuffsDisable` : This DISABLES the images and text auras. It is HIGHLY recommended you only do this if you have the TTS option ENABLED.  

//todo : add pictures, maybe
### Copy Settings Locally

//TODO!

## FAQ & Troubleshoting
//TODO : will fill this as common questions come.