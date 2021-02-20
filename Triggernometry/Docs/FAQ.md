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
  - [How do i add/import triggers (not repos) ?](#how-do-i-addimport-triggers-not-repos-)
  - [How do i enable Dev mode ?](#how-do-i-enable-dev-mode-)
  - [How can i tell if my trigger/folder is active ?](#how-can-i-tell-if-my-triggerfolder-is-active-)
  - [What do the colors/icons mean ?](#what-do-the-colorsicons-mean-)
  - [About "Fire" (Force/Test Fire)](#about-fire-forcetest-fire)
- [Making Triggers: Basics](#making-triggers-basics)
  - [Accessing Regex Groups](#accessing-regex-groups)
  - [Adding Conditions to a Trigger](#adding-conditions-to-a-trigger)
- [Making Triggers: Advanced](#making-triggers-advanced)
  - [Gauge Line](#gauge-line)
    - [Network (`1F:`)](#network-1f)
      - [Example 1 : RDM](#example-1--rdm)

# Repos FAQ

## What does each repo do ?

-   `Combat & Duties by Aho Senpai`:
    -   `Aho's Dungeons`: This contains triggers for most dungeons. It is sorted by FFXIV expansion (ARR => HW => SB => ShB) and then sorted by instance level. This also contains BLU Masked Carnival triggers as well as Deep Dungeons (PotD & HoH)
    -   `Aho's Eureka & Bozja`: This contains Eureka and Bozja triggers. (Honnestly, if you are looking for a eureka map tracker, check out [cactbot](https://github.com/quisquous/cactbot))
    -   `Aho's Jobs`: This contains triggers for all FFXIV Battle Jobs. It is sorted by Role then Job.
    -   `Aho's Raid Buffs`: This contains triggers for raid buffs. This is aura-based (a "rework" is WIP)
    -   `Aho's Raids`: This contains triggers for most raids. It is sorted by Type (8-Man, Alliance, Ultimate) then by FFXIV expansion (ARR => HW => SB => ShB) (Ultimate is the exception as there is very few of them) then by instance level.
    -   `Aho's Trials`: This contains triggers for most trials. It is sorted by FFXIV expansion (ARR => HW => SB => ShB) and then sorted by instance level.
    -   `Miscellaneous`: This contains various triggers such as `Wipe or Clear Reset` which ends the ACT encounter on wipe or clear, or aura triggers for `Pull Duration` and `Countdown`

## Where do i get those "repos" ?

1. Select the `Remote triggers` folder.
1. In the Top Left, click on `Add`
1. Select `Repository from list`
1. Check the repositories you want. Please do NOT select every single repository unless you want and need all of them.
1. In the Bottom Left, click on `Add Selected`
1. Congratulations!

## I have an issue with <x> trigger/repo !

You can:

-   Submit an [Issue on the GitHub](./ISSUES.md)
-   Ask in [Triggernometry Discord](https://discord.gg/6f9MY55)
-   Ask in my [GitHub Project Discord](https://discord.gg/dPFSM53)
-   DM me on Discord (Aho Senpai#0818)

## How can I help ?

You can :

-   Provide logs (ideally using a [gist](https://gist.github.com/))
-   Provide information on what ability does what (at least for the more "common" mechanics, like raid-wide damage or tank-busters)
-   [CONTRIBUTE](./CONTRIBUTE.md)

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

## How do i update Triggernometry ?

1. THIS ASSUMES YOU ALREADY HAVE TRIGGERNOMETRY INSTALLED
1. Download the [LATEST](https://github.com/paissaheavyindustries/Triggernometry/releases/latest) version.
1. Extract the ZIP
1. At this point, if you still have ACT open, CLOSE IT.
1. Relace the file `Triggernometry.dll` in your ACT Folder (`C:\Users\<USER>\AppData\Roaming\Advanced Combat Tracker\Plugins` by default).
1. This should ask you if you want to overwrite the file. If it does not, check that you did the previous steps.
1. Open ACT. If you get a prompt about a blocked file, click `Yes` to unblock it.
1. Congratulations.

NOTE: If your `.dll` file is not in the ACT Plugin folder, it is greatly encouraged that you do move it there.

## How do i add/import triggers (not repos) ?

1. Select the folder where you want to import your trigger.
1. Top Right => `Import`
1. (Personal recommendation: copy the link of the file, assuming you have it as a file of course, and paste the URL in the second text field (after selecting it) Note that discord links also work (assuming said link points to a file, obviously))
1. `Next` will allow you to view what you are importing. You can also look into the triggers themselves at this point (and even remove if you want, tho not recommended).
1. Lastly, `Import` will finish this process.

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

# Making Triggers: Basics

First, if you are unfamilar with what RegEx is, i highly encourage you to document yourself on it.  
[My Basic Regex Explanation](../../Documentation/Let's%20Talk%20REGEX.md)  
[My Example at making a Auto-Attack Regex](../../Documentation/Let's%20Talk%20REGEX.md)

Also keep this document open, it's very useful reference as you make triggers [Triggernometry FAQ](https://github.com/paissaheavyindustries/Triggernometry/wiki/Triggernometry-FAQ-and-examples)  
Now, let's see what we can do with triggernometry action and conditions

## Accessing Regex Groups

Consider the following regex (note that this regex isn't actually useful, just an example)  
`14:(?<PlayerID>.{8}):(?<PlayerName>.{3,21}):0F5C:00:`  
Here, i have 2 ways to access the regex groups :

-   `${PlayerID}` and `${PlayerName}`
-   `$1` and `$2` (`$1` referencing the first capture group, `PlayerID` in this case)

So far, not too complicated right ? However, consider this regex:  
`14:(.{8}):(?<thing>.{5,23}):(?>00):([45][31][71]):`  
Now, as you may notice, referencing groups becomes a bit more ... annoying:  
The first and fourth group `(.{8})` and `([45][31][71])` can only be accessed with `$1` and `$3` respectively since they don't have a name, while the second group can be accessed by both `$2` and `${thing}`. The third group isn't a capture group, and thus cannot be referenced, which is why the fourth group gets called by `$3`.

Sounds confusing ? Yeah, you can understand why i personally recommend naming all your capture groups, not only does it makes more sense (with relevant names of course), it also allow other people looking at it to understand what you are doing.

## Adding Conditions to a Trigger

Let's take the Auto-Attack regex we made in [My Example at making a Auto-Attack Regex](../../Documentation/Let's%20Talk%20REGEX.md)  
`\[.{14}15:[A-F0-9]{8}:(?<player>[a-zA-Z-' ]{3,21}):07:`  
(i removed the `Attack:` part, as to make it language agnostic)

Now, After selecting the folder you want to create this trigger in, you can select `Trigger` in the dropdown menu in the Top Left  
Give it a name. Ideally something that makes sense. Let's call this trigger `Auto-Attack Example` and put the regex in said field.  
Great, but this doesn't do anything yet, and will trigger everytime anyone do an Auto-Attack. Let's `Add action` something simple for now, to check when this trigger is going odd. A `System beep` will do just fine.  
Now, if you save and test it in-game, it goes off all the time. Let's add a condition : `Trigger condition` tab will let us add conditions on the trigger firing.  
`Add` -> `Condition`  
Now, we will want to compare the regex capture group `${player}` with our own player name. Triggernometry offers a couple ways to do this, but the simpler being `${_ffxivplayer}`  
Let's put this in the corresponding fields :  
`${player}` on the "Left expression"  
`${_ffxivplayer}` in the "Right expression"  
Make sure you also select the correct `Operator`. In this case we can leave it as default.  
Also make sure the expression types correspond to what you are evaluating. `String` in this case.  
Lastly, you will want to check the parent condition groups so that the condition you do want isn't <span style="color: red;">red<span/>

Great, now you may notice the trigger is only going off when YOU use an Auto-Attack.  
[Result Trigger](https://raw.githubusercontent.com/Aho-Senpai/Aho-Triggers/main/Triggernometry/Docs/resources/Auto-Attack_Example.xml)  
[How to import](#how-do-i-addimport-triggers-not-repos-)

# Making Triggers: Advanced

## Gauge Line

### Network (`1F:`)

[Cactbot JobGauge LogGuide Section](https://github.com/quisquous/cactbot/blob/main/docs/LogGuide.md#1f-networkgauge)

[Dalamud JobGauge Structure Doc](https://github.com/goatcorp/Dalamud/tree/master/Dalamud/Game/ClientState/Structs/JobGauge)

#### Example 1 : RDM

What interests us in this is this part (taking RDM as example)

```
public struct RDMGauge {
    [FieldOffset(0)] public byte WhiteGauge;
    [FieldOffset(1)] public byte BlackGauge;
}
```

let's make it clearer if you aren't familar with C# or coding languages.

```
Offset (0) byte WhiteGauge;
Offset (1) byte BlackGauge;
```
Ok, but how do i read that ? WTF does that mean ?
It means that the first `byte` will represent `WhiteGauge` and the second `byte` will represent `BlackGauge`  
A `byte` is a number between `0` and `255`. `255` in Hex = `0xFF`. Meaning it will be 2 characters at most. This will be important later when tackling "more complex" job gauges. For now, keep in mind that `byte` = we are looking at a 2 character.

With this we now know what part of the logline is what. (Simple example to start)  
Now, here's what ACT log lines for it will look like

```
[00:00:00.000] 1F:00000000:Player Name:723:2000000:00:00
[00:00:00.000] 1F:00000000:Player Name:30A23:2000000:00:00
[00:00:00.000] 1F:00000000:Player Name:60D23:2000000:00:00
[00:00:00.000] 1F:00000000:Player Name:110D23:2000000:00:00
[00:00:00.000] 1F:00000000:Player Name:141023:2000000:00:00
[00:00:00.000] 1F:00000000:Player Name:141B23:2000000:00:00
[00:00:00.000] 1F:00000000:Player Name:142423:2000000:00:00
[00:00:00.000] 1F:00000000:Player Name:1F2423:2000000:00:00
[00:00:00.000] 1F:00000000:Player Name:282423:2000000:00:00
[00:00:00.000] 1F:00000000:Player Name:282F23:2000000:00:00
[00:00:00.000] 1F:00000000:Player Name:283823:2000000:00:00
[00:00:00.000] 1F:00000000:Player Name:333823:2000000:00:00
[00:00:00.000] 1F:00000000:Player Name:646423:2000000:00:00
```

Now, the part that do interest us is after `Player Name`  
Let's take the last line as example and eliminate noise :  
`:646423:`  
Keep in mind that now we have to `PadLeft` to get 8 characters total.  
`:00646423:`  
And then reverse it by group of 2 characters. Let's space it as well for readabiulity  
`23 64 64 00` With this and previous linked doc, we know what is what

| Job | White Mana | Black Mana | (nothing) |
| :-: | :--------: | :--------: | :-------: |
| 23  |     64     |     64     |    00     |

Now, we convert said values from Hex to Dec: `0x64 = 100`  
(The job stays as Hex, unless you _need_ to convert it)

Great, now we can make a regex for it and slap that in a trigger  
(This will assume you have some non-0 amount of understanding of RegEx)

`\[.{14}1F:[A-F0-9]{8}:[a-zA-Z-' ]{3,21}:(?<BlackMana>[A-F0-9]{0,2}?)?(?<WhiteMana>[A-F0-9]{0,2}?)?23:`  
Here, we need to do sone "trickery" to make sure we always get 2 characters from right to left, hence the `(?<group>[x]{0,2}?)?`

Now, how to reference it in a trigger action ? Well, we will need to do what we did earlier: convert Hex2Dec. We won't need to do much more in this case (RDM) as the data we are looking for is all nice and simple, and can be "isoalted" nicely with regex. So, using Triggernometry syntax, we will get something like this `hex2dec(${WhiteMana})`  
If you are using a text field (you can tell by hovering over the trigger icon on the left of the field), you will want to wrap it in a `${numeric: }`  
`${numeric:hex2dec(${WhiteMana})}`

Great! Now all that's left to do if for you to "finalise" the trigger.  
Note that Gauge triggers don't _need_ to have player-check, as you will only see your own gauge lines; other players gauge data isn't sent to your FFXIV client.  
[Here is an example trigger for RDM Gauge](https://raw.githubusercontent.com/Aho-Senpai/Aho-Triggers/main/Triggernometry/Docs/resources/RDM_Gauge_Example.xml)  
[How to import](#how-do-i-addimport-triggers-not-repos-)  
(Note: You will need at least Triggernometry version BETA: `Triggernometry_1_1_4_0_b2` for this trigger to work properly)  
(TO DO: Change note when version is out of beta)
