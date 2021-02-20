<h1 style="text-align:center">FAQ</h1>

<h2>Table of Contents</h2>  

- [Repos FAQ](#repos-faq)
  - [What does each repo do ?](#what-does-each-repo-do-)
  - [Where do i get those "repos" ?](#where-do-i-get-those-repos-)
  - [I have an issue with <x> trigger/repo !](#i-have-an-issue-with-x-triggerrepo-)
  - [How can I help ?](#how-can-i-help-)
- [Triggernometry FAQ](#triggernometry-faq)
  - [How to install Triggernometry ?](#how-to-install-triggernometry-)
  - [How do i update Triggernometry ?](#how-do-i-update-triggernometry-)
  - [How do i enable Dev mode ?](#how-do-i-enable-dev-mode-)
  - [How can i tell if my trigger/folder is active ?](#how-can-i-tell-if-my-triggerfolder-is-active-)
  - [What do the colors/icons mean ?](#what-do-the-colorsicons-mean-)
  - [About "Fire" (Force/Test Fire)](#about-fire-forcetest-fire)

# Repos FAQ

## What does each repo do ?

- `Combat & Duties by Aho Senpai`:
  - `Aho's Dungeons`: This contains triggers for most dungeons. It is sorted by FFXIV expansion (ARR => HW => SB => ShB) and then sorted by instance level.
  This also contains BLU Masked Carnival triggers as well as Deep Dungeons (PotD & HoH)
  - `Aho's Eureka & Bozja`: This contains Eureka and Bozja triggers. (Honnestly, if you are looking for a eureka map tracker, check out [cactbot](https://github.com/quisquous/cactbot))
  - `Aho's Jobs`: This contains triggers for all FFXIV Battle Jobs. It is sorted by Role then Job.
  - `Aho's Raid Buffs`: This contains triggers for raid buffs. This is aura-based (a "rework" is WIP)
  - `Aho's Raids`: This contains triggers for most raids. It is sorted by Type (8-Man, Alliance, Ultimate) then by FFXIV expansion (ARR => HW => SB => ShB) (Ultimate is the exception as there is very few of them) then by instance level. 
  - `Aho's Trials`: This contains triggers for most trials. It is sorted by FFXIV expansion (ARR => HW => SB => ShB) and then sorted by instance level.
  - `Miscellaneous`: This contains various triggers such as `Wipe or Clear Reset` which ends the ACT encounter on wipe or clear, or aura triggers for `Pull Duration` and `Countdown`

## Where do i get those "repos" ?

1. Select the `Remote triggers` folder.
1. In the Top Left, click on `Add`
1. Select `Repository from list`
1. Check the repositories you want. Please do NOT select every single repository unless you want and need all of them.
1. In the Bottom Left, click on `Add Selected`
1. Congratulations!  

## I have an issue with <x> trigger/repo !

You can:
- Submit an [Issue on the GitHub](./ISSUES.md)
- Ask in [Triggernometry Discord](https://discord.gg/6f9MY55) 
- Ask in my [GitHub Project Discord](https://discord.gg/dPFSM53)
- DM me on Discord (Aho Senpai#0818)  

## How can I help ?

You can :
- Provide logs (ideally using a [gist](https://gist.github.com/))
- Provide information on what ability does what (at least for the more "common" mechanics, like raid-wide damage or tank-busters)  
- [CONTRIBUTE](./CONTRIBUTE.md)


# Triggernometry FAQ

This part will cover a wide range of questions frequently asked in Triggernometry Discord.

## How to install Triggernometry ?

1. Download the [LATEST](https://github.com/paissaheavyindustries/Triggernometry/releases/latest) version.
1. Extract the ZIP
1. Place the file `Triggernometry.dll` in your ACT Folder (`C:\Users\<USER>\AppData\Roaming\Advanced Combat Tracker\Plugins` by default).
1. In ACT, go to the `Plugins` => `Plugin Listing` => `Browse` and locate the file from the previous step. Click `Open`
1. Click `Add/Enable Plugin`. If you get a prompt about a blocked file, click `Yes` to unblock it.
1. Congratulations. Now navigate to the `Triggernometry` tab and read the welcome screen.

NOTE: While you can put the `.dll` file whereever you want, it is NOT encouraged as it invites more variables for troubleshooting.

##  How do i update Triggernometry ?

1. THIS ASSUMES YOU ALREADY HAVE TRIGGERNOMETRY INSTALLED
1. Download the [LATEST](https://github.com/paissaheavyindustries/Triggernometry/releases/latest) version.
1. Extract the ZIP
1. At this point, if you still have ACT open, CLOSE IT.
1. Relace the file `Triggernometry.dll` in your ACT Folder (`C:\Users\<USER>\AppData\Roaming\Advanced Combat Tracker\Plugins` by default).
1. This should ask you if you want to overwrite the file. If it does not, check that you did the previous steps.
1. Open ACT. If you get a prompt about a blocked file, click `Yes` to unblock it.
1. Congratulations.

NOTE: If your `.dll` file is not in the ACT Plugin folder, it is greatly encouraged that you do move it there.

## How do i enable Dev mode ?

1. Top Right => `Options`
1. `Edit Configuration`
1. `Miscellaneous` Tab
1. Check `Developer mode`

## How can i tell if my trigger/folder is active ?

If the checkbox is checked, ![CB_On](./resources/CB_On.PNG) it's enabled/active,  
If it's not checked ![CB_Off](./resources/CB_Off.PNG) it's NOT enabled/active, and if it's a folder, anything inside it is also disabled.

## What do the colors/icons mean ?

![Blue_Folder](./resources/Blue_Folder.PNG) This is a regular folder  
![Purple_folder](./resources/Purple_Folder.PNG) This is a folder that has a "lock" (can be zone or job lock)  
![Repository](./resources/Repository.PNG) This is a regular repository  
![Disabled_Repo](./resources/Disabled_Repository.PNG) This is a disabled repository  
![ReadMe_Icon](./resources/ReadMe_Icon.PNG) This is a README icon. THIS IS IMPORTANT. READ IT.  

## About "Fire" (Force/Test Fire)

This FORCES fire a trigger. To do that, it WILL have to ignore some things (conditions) and set other things (variables) using placeholder values.  
This is a good way to test if your actions do what you expect, but it is NOT a good way to test if your conditions work.