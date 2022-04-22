<h1 style="text-align:center">FAQ</h1>

<h2>Table of Contents</h2>

- [Repos FAQ](#repos-faq)
  - [What does each repo do ?](#what-does-each-repo-do-)
  - [Where do i get those "repos" ?](#where-do-i-get-those-repos-)
  - [I have an issue with <x> trigger/repo !](#i-have-an-issue-with-x-triggerrepo-)
  - [How can I help ?](#how-can-i-help-)
  - [Discord Callouts Ready](#discord-callouts-ready)
- [Triggernometry FAQ](#triggernometry-faq)
  - [How to install Triggernometry ?](#how-to-install-triggernometry-)
  - [How do i update Triggernometry ?](#how-do-i-update-triggernometry-)
  - [How do i add/import triggers (not repos) ?](#how-do-i-addimport-triggers-not-repos-)
  - [How do i enable Dev mode ?](#how-do-i-enable-dev-mode-)
  - [How can i tell if my trigger/folder is active ?](#how-can-i-tell-if-my-triggerfolder-is-active-)
  - [What do the colors/icons mean ?](#what-do-the-colorsicons-mean-)
  - [About "Fire" (Force/Test Fire)](#about-fire-forcetest-fire)
  - [How do I change the TTS voice ?](#how-do-i-change-the-tts-voice-)
  - [How do i make a trigger ?](#how-do-i-make-a-trigger-)
  - [How do i add an action to a trigger ?](#how-do-i-add-an-action-to-a-trigger-)
- [Making Triggers: Basics](#making-triggers-basics)
  - [Accessing Regex Groups](#accessing-regex-groups)
  - [Adding Conditions to a Trigger](#adding-conditions-to-a-trigger)
- [Making Triggers: Advanced](#making-triggers-advanced)
  - [Gauge Line](#gauge-line)
    - [Encounter Logs (`1F:`)](#encounter-logs-1f)
      - [Example 1 : RDM](#example-1--rdm)
      - [Example 2 : SCH](#example-2--sch)
      - [Example 3 : DNC](#example-3--dnc)
      - [Example 4 : BLM](#example-4--blm)
- [Thanks](#thanks)

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

-   Provide logs (ideally using a [gist](https://gist.github.com/) or any pastebin-like [Pastebin](https://pastebin.com/), [Paste.gg](https://paste.gg/), or any of your choice)
-   Provide information on what ability does what (at least for the more "common" mechanics, like raid-wide damage or tank-busters)
-   [CONTRIBUTE](./CONTRIBUTE.md)

## Discord Callouts Ready

__<ins>IMPORTANT:</ins>__ This assumes you alreaady have a discord bot as well as [Makar8000 Plugin setup](https://github.com/Makar8000/ACT-Discord-Triggers/wiki/First-Time-Setup-Guide) (ACT Discord Triggers)

You will also need to have set the options in `Options > Edit configuration > audio > ACT hooks` to be checked.

So, now that you do, what's this about ? well, mainly the `Raid` repo has callouts meant with this in mind : having them go through a discord bot.  

Well, all the relevant callouts at least. All the more personal callouts will stay "local" (aka, not go through the discord bot).  

Q."I don't use a discord bot, how does this affect me?"  
A. It doesn't.  

Q."I don't want this behavious to happen, how do i do that ?"  
A. you can set the 'Audio output setting override' to 'on'.

Q. "I want to use it with a discord bot but everything goes through the bot"  
A. : 
1. Make sure the Repo Settings are correct : Audio output setting override -> "As defined in repository"
1. Make sure your Triggernometry Soud settings are correct : Use ACT for Text-To-Speech -> Checked


# Triggernometry FAQ

This part will cover a wide range of questions frequently asked in Triggernometry Discord.

## How to install Triggernometry ?

Automatically :  
1. `Advanced Combat Tracker` => `Plugins` => `Plugin Listing` => TOP RIGHT `Get Plugins`
1. Select `Triggernometry` => `Download and Enable`
1. Congratulations. Now navigate to the `Triggernometry` tab and read the welcome screen.

Manually :
1. Download the [LATEST](https://github.com/paissaheavyindustries/Triggernometry/releases/latest) version.
1. Extract the ZIP
1. Place the file `Triggernometry.dll` in your ACT Folder (`C:\Users\<USER>\AppData\Roaming\Advanced Combat Tracker\Plugins` by default).
1. In ACT, go to the `Plugins` => `Plugin Listing` => `Browse` and locate the file from the previous step. Click `Open`
1. Click `Add/Enable Plugin`. If you get a prompt about a blocked file, click `Yes` to unblock it.
1. Congratulations. Now navigate to the `Triggernometry` tab and read the welcome screen.

NOTE: While you can put the `.dll` file whereever you want, it is NOT encouraged as it invites more variables for troubleshooting.

## How do i update Triggernometry ?

<!-- TODO : Add update steps -->

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

## How do I change the TTS voice ?

Here, you have a few options : 

- Change windows TTS voice (ACT -> Options -> Sound Settings -> "Text to Speech Control Pannel Applet")
- Install a TTS plugin (such as yukkuri (part of [Hojoring](https://github.com/anoyetta/ACT.Hojoring)))

## How do i make a trigger ?

- Select the folder where you want to add a trigger  
- Top Right > `Add`  
- `Trigger`
- Now, at least give it a name and `Save`
- Congratulations, you created a trigger.

## How do i add an action to a trigger ?

- Select the desired trigger
- In the `Trigger action` tab (the one open by default) select `Add action`
- At the top of the new window, select the action type in the list
- Now make the action do what you want.
- Congratulations, you created a trigger action.

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

### Encounter Logs (`1F:`)

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
Offset (0) byte WhiteGauge
Offset (1) byte BlackGauge
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

|  Job  | White Mana | Black Mana | (nothing) |
| :---: | :--------: | :--------: | :-------: |
|  23   |     64     |     64     |    00     |

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

#### Example 2 : SCH

```
public struct SCHGauge {
    [FieldOffset(2)] public byte NumAetherflowStacks;
    [FieldOffset(3)] public byte FairyGaugeAmount;
    [FieldOffset(4)] public short SeraphTimer;
    [FieldOffset(6)] public byte DismissedFairy;
}
```

Once again, let's make it easier to read

```
Offset (2) byte     NumAetherflowStacks
Offset (3) byte     FairyGaugeAmount
Offset (4) ushort   SeraphTimer
Offset (6) byte     DismissedFairy
```

Here things get a bit more interesting : he have a `ushort`.  
But ... what's a `ushort` ? It's a value between `0` and `65535`.  
And you might have guessed it, but `65535` = `0xFFFF`. So we are looking at a 4 character.

Ok, let's see what SCH gauge lines look like

```
[00:00:00.000] 1F:00000000:Player Name:300001C:00:00:00
[00:00:00.000] 1F:00000000:Player Name:200001C:0A:00:00
[00:00:00.000] 1F:00000000:Player Name:100001C:14:00:00
[00:00:00.000] 1F:00000000:Player Name:1C:1E:00:00
[00:00:00.000] 1F:00000000:Player Name:300001C:700001E:00:00
[00:00:00.000] 1F:00000000:Player Name:200001C:700001E:00:00
[00:00:00.000] 1F:00000000:Player Name:100001C:700001E:00:00
[00:00:00.000] 1F:00000000:Player Name:1C:700001E:00:00
[00:00:00.000] 1F:00000000:Player Name:1C:1E:00:00
[00:00:00.000] 1F:00000000:Player Name:1C:14:00:00
[00:00:00.000] 1F:00000000:Player Name:1C:0A:00:00
[00:00:00.000] 1F:00000000:Player Name:300001C:0A:00:00
[00:00:00.000] 1F:00000000:Player Name:200001C:14:00:00
[00:00:00.000] 1F:00000000:Player Name:100001C:1E:00:00
[00:00:00.000] 1F:00000000:Player Name:100001C:14:00:00
[00:00:00.000] 1F:00000000:Player Name:1C:1E:00:00
[00:00:00.000] 1F:00000000:Player Name:1C:14:00:00
[00:00:00.000] 1F:00000000:Player Name:1C:0A:00:00
[00:00:00.000] 1F:00000000:Player Name:1C:755F00A:00:00
```

So from `1F:00000000:Player Name:300001C:700001E:00:00`, we get something like  
`300001C` => `0300001C` => `03 00 00 1C`  
But wait ... that doesn't seem right, we are looking for more than just 3 `byte` ...  
Yes, we need to take the next bit of data as well.  
`:0300001C:0700001E:` => `:0300001C:0700001E` => `0300001C0700001E`  
Ok, now we can just split it right ? Well, no we need to flip them separately, then put them together  
`0300001C 0700001E` => `03 00 00 1C   07 00 00 1E ` => `1C 00 00 03 1E 00 00 07`  
Now, here's the fun part: remember the `Offset` ? it now comes into play.  
|  Job  | (nothing) | (nothhing) | AF stacks | Fairy gauge | Seraph timer | Dismissed fairy |
| :---: | :-------: | :--------: | :-------: | :---------: | :----------: | :-------------: |
|  1C   |    00     |     00     |    03     |     1E      |     0000     |       07        |

Now it should become quite clear right ?  
Well, time to make a regex for it.  
`\[.{14}1F:[A-F0-9]{8}:[a-zA-Z-' ]{3,21}:(?<AetherFlow>\d)?(?>0{0,4})1C:(?<DismissedFairy>\d??)?(?<SeraphTimer>[A-F0-9]{0,4}?)?(?<fairyGauge>[A-F0-9]{1,2})?:`  
Yes. If you are confused by it, put the regex and the test lines in a regex-website (such as [Regex101](https://regex101.com/) and play around with it)  
Taking the last line as an example, we can see we get `55F0` for SeraphTimer. `0x55F0` = `22000`. Which means 22 Seconds. That's also Seraph duration. Looks good.


#### Example 3 : DNC

```
public struct DNCGauge {
    [FieldOffset(0)] byte NumFeathers;
    [FieldOffset(1)] byte Esprit;
    [FieldOffset(2)] byte StepOrder1;
    [FieldOffset(3)] byte StepOrder2;
    [FieldOffset(4)] byte StepOrder3;
    [FieldOffset(5)] byte StepOrder4;
    [FieldOffset(6)] byte StepsCombo;
}
```
Once again, readability for everyone :
```
Offset (0) byte NumFeathers
Offset (1) byte Esprit

Offset (2) byte StepOrder1
Offset (3) byte StepOrder2
Offset (4) byte StepOrder3
Offset (5) byte StepOrder4

Offset (6) byte StepsCombo
```
Wow, that's a lot isn't it. It's ok, it will all make sense with time. Let's look at what gauge lines look like for DNC:
```
[00:00:00.000] 1F:00000000:Player Name:A0026:00:00:00
[00:00:00.000] 1F:00000000:Player Name:140026:00:00:00
[00:00:00.000] 1F:00000000:Player Name:140126:00:00:00
[00:00:00.000] 1F:00000000:Player Name:1E0126:00:00:00
[00:00:00.000] 1F:00000000:Player Name:280126:00:00:00
[00:00:00.000] 1F:00000000:Player Name:280226:00:00:00
[00:00:00.000] 1F:00000000:Player Name:320226:00:00:00
[00:00:00.000] 1F:00000000:Player Name:226:00:00:00
[00:00:00.000] 1F:00000000:Player Name:4000226:02:00:00
[00:00:00.000] 1F:00000000:Player Name:4000226:1000002:00:00
[00:00:00.000] 1F:00000000:Player Name:4000226:2000002:00:00
[00:00:00.000] 1F:00000000:Player Name:226:00:00:00
[00:00:00.000] 1F:00000000:Player Name:326:00:00:00
[00:00:00.000] 1F:00000000:Player Name:A0326:00:00:00
[00:00:00.000] 1F:00000000:Player Name:A0226:00:00:00
[00:00:00.000] 1F:00000000:Player Name:A0126:00:00:00
[00:00:00.000] 1F:00000000:Player Name:A0226:00:00:00
[00:00:00.000] 1F:00000000:Player Name:140226:00:00:00
[00:00:00.000] 1F:00000000:Player Name:3140226:01:00:00
[00:00:00.000] 1F:00000000:Player Name:3140226:1000001:00:00
[00:00:00.000] 1F:00000000:Player Name:3140226:2000001:00:00
[00:00:00.000] 1F:00000000:Player Name:140226:00:00:00
[00:00:00.000] 1F:00000000:Player Name:1E0226:00:00:00
[00:00:00.000] 1F:00000000:Player Name:1E0326:00:00:00
[00:00:00.000] 1F:00000000:Player Name:280326:00:00:00
[00:00:00.000] 1F:00000000:Player Name:280226:00:00:00
[00:00:00.000] 1F:00000000:Player Name:2280226:30401:00:00
[00:00:00.000] 1F:00000000:Player Name:2280226:1030401:00:00
[00:00:00.000] 1F:00000000:Player Name:2280226:2030401:00:00
[00:00:00.000] 1F:00000000:Player Name:2280226:3030401:00:00
[00:00:00.000] 1F:00000000:Player Name:2280226:4030401:00:00
[00:00:00.000] 1F:00000000:Player Name:280226:00:00:00
[00:00:00.000] 1F:00000000:Player Name:320226:00:00:00
[00:00:00.000] 1F:00000000:Player Name:320326:00:00:00
[00:00:00.000] 1F:00000000:Player Name:320226:00:00:00
[00:00:00.000] 1F:00000000:Player Name:226:00:00:00
```
Lots of test data is good, it allows to increase the chances of getting all the cases. For our purpose, let's take a line with the most amount of gauge data ... This one seems good.
`1F:00000000:Player Name:4000226:1000002:00:00`  
`:4000226:1000002:` Ok, let's break it down, flip it and do magic.
`:04000226:01000002:` => `04000226  01000002` => `04 00 02 26  01 00 00 02`  
`26 02 00 04  02 00 00 01`  
Ok, now let's map everything.
|  Job  | Feathers | Esprit | Step1 | Step2 | Step3 | Step4 | StepsCombo |
| :---: | :------: | :----: | :---: | :---: | :---: | :---: | :--------: |
|  26   |    02    |   00   |  04   |  02   |  00   |  00   |     01     |

Ok, looking good. Let's make the regex for it.  
`\[.{14}1F:[A-F0-9]{8}:[a-zA-Z-' ]{3,21}:(?<Step1>[1-4]{0,1}?)?(?<Esprit>[A-F0-9]{0,2}?)?(?<Feathers>[0-4]{1,2})?26:(?<StepsCombo>[0-4]?)??(?<Step4>[0-4]{0,2}?)?(?<Step3>[0-4]{0,2}?)?(?<Step2>[0-4]{2}?):`  
Yep, once again, if you are confused put the regex and the test lines in a regex-website (such as [Regex101](https://regex101.com/) and play around with it)  

By the way, the corresponding steps can be found in cactbot Doc :
```
None = 0,
Emboite = 1,
Entrechat = 2,
Jete = 3,
Pirouette = 4,
```

#### Example 4 : BLM
```
 public struct BLMGauge {
    [FieldOffset(0)] public ushort TimeUntilNextPolyglot;  //eno timer (ms)
    [FieldOffset(2)] public ushort ElementTimeRemaining;  //ui/af timer
    [FieldOffset(4)] private sbyte ElementStance; //ui/af
    [FieldOffset(5)] public byte NumUmbralHearts; //number of umbral hearts
    [FieldOffset(6)] public byte NumPolyglotStacks; //number of polyglot stacks
    [FieldOffset(7)] private byte EnoState; // Bit 0 = Enochian active. Bit 1 = Polygot active.
}
```
More Formatting
```
Offset (0)  ushort  TimeUntilNextPolyglot
Offset (2)  ushort  ElementTimeRemaining
Offset (4)  sbyte   ElementStance
Offset (5)  byte    NumUmbralHearts
Offset (6)  byte    NumPolyglotStacks
Offset (7)  byte    EnoState
```
And more data
```
[00:00:00.000] 1F:00000000:Player Name:98000019:FD3A:00:00
[00:00:00.000] 1F:00000000:Player Name:D1753019:FD37:01:00
[00:00:00.000] 1F:00000000:Player Name:9864D919:33A:01:00
[00:00:00.000] 1F:00000000:Player Name:982BBD19:33A:01:00
[00:00:00.000] 1F:00000000:Player Name:98099D19:33A:01:00
[00:00:00.000] 1F:00000000:Player Name:9800E919:FD3A:01:00
[00:00:00.000] 1F:00000000:Player Name:8E753019:100FD39:01:00
[00:00:00.000] 1F:00000000:Player Name:CA6B6C19:103FD2F:01:00
[00:00:00.000] 1F:00000000:Player Name:C9676B19:3FD2B:01:00
[00:00:00.000] 1F:00000000:Player Name:985CA419:3033A:01:00
[00:00:00.000] 1F:00000000:Player Name:CD51D919:2032F:01:00
[00:00:00.000] 1F:00000000:Player Name:C148CD19:10326:01:00
[00:00:00.000] 1F:00000000:Player Name:503E5C19:31C:01:00
[00:00:00.000] 1F:00000000:Player Name:982A5E19:33A:401:419C72AE
[00:00:00.000] 1F:00000000:Player Name:98079B19:33A:01:00
[00:00:00.000] 1F:00000000:Player Name:9800A719:FD3A:01:00
[00:00:00.000] 1F:00000000:Player Name:E5753019:100FD39:01:00
[00:00:00.000] 1F:00000000:Player Name:DA682519:103FD2C:01:00
[00:00:00.000] 1F:00000000:Player Name:6C65B719:3FD2A:401:4091E336
[00:00:00.000] 1F:00000000:Player Name:984E6619:3033A:01:00
[00:00:00.000] 1F:00000000:Player Name:BB418919:2032D:01:00
[00:00:00.000] 1F:00000000:Player Name:2A33F819:10320:01:00
[00:00:00.000] 1F:00000000:Player Name:BC298A19:315:01:00
[00:00:00.000] 1F:00000000:Player Name:98153019:33A:01:00
[00:00:00.000] 1F:00000000:Player Name:53753019:1000325:01:00
[00:00:00.000] 1F:00000000:Player Name:98684C19:100033A:01:00
[00:00:00.000] 1F:00000000:Player Name:98615619:100FD3A:01:00
[00:00:00.000] 1F:00000000:Player Name:BF547D19:103FD2D:01:00
[00:00:00.000] 1F:00000000:Player Name:4E520C19:3FD2B:01:00
[00:00:00.000] 1F:00000000:Player Name:983B7819:3033A:01:00
[00:00:00.000] 1F:00000000:Player Name:BB2E9B19:2032D:01:00
[00:00:00.000] 1F:00000000:Player Name:4E242E19:10323:202C3101:3A6E696D
[00:00:00.000] 1F:00000000:Player Name:84196419:318:01:00
[00:00:00.000] 1F:00000000:Player Name:980F1619:33A:01:00
[00:00:00.000] 1F:00000000:Player Name:76753019:100032B:01:00
[00:00:00.000] 1F:00000000:Player Name:9857D319:100033A:01:00
[00:00:00.000] 1F:00000000:Player Name:9850B319:100FD3A:01:00
[00:00:00.000] 1F:00000000:Player Name:D842F319:FD2C:01:00
[00:00:00.000] 1F:00000000:Player Name:9835BE19:33A:01:00
[00:00:00.000] 1F:00000000:Player Name:C7753019:1000304:01:00
[00:00:00.000] 1F:00000000:Player Name:98747E19:100033A:01:00
[00:00:00.000] 1F:00000000:Player Name:98605419:100FD3A:01:00
[00:00:00.000] 1F:00000000:Player Name:D0528C19:FD2C:01:00
[00:00:00.000] 1F:00000000:Player Name:B9417519:3FD1B:01:00
[00:00:00.000] 1F:00000000:Player Name:983A4E19:3033A:01:00
[00:00:00.000] 1F:00000000:Player Name:C42B7A19:2032B:01:00
[00:00:00.000] 1F:00000000:Player Name:CE208419:10320:202C3401:3A6E696D
```

Usual `PadLeft` and flip  

`BF547D19:103FD2D:` => `BF 54 7D 19  01 03 FD 2D` => `19 7D 54 BF   2D FD 03 01`  

|  Job  | TimeUntilNextPolyglot | ElementTimeRemaining | ElementStance | NumUmbralHearts | umPolyglotStacks | EnoState |
| :---: | :-------------------: | :------------------: | :-----------: | :-------------: | :--------------: | :------: |
|  19   |         7D54          |         BF2D         |      FD       |       03        |        01        |

And here we are. missing on data. thus, we need to grab more than just the 2 groups. we need to grab the 3rd group as well

`:4E242E19:10323:202C3101:` => `4E242E19 00010323 202C3101` => `19 2E 24 4E   23 03 01 00   01 31 2C 20`  
But, here we don't care about all of it. we'll fix that in the regex.
|  Job  | TimeUntilNextPolyglot | ElementTimeRemaining | ElementStance | NumUmbralHearts | umPolyglotStacks | EnoState | (unneeded) |
| :---: | :-------------------: | :------------------: | :-----------: | :-------------: | :--------------: | :------: | :--------: |
|  19   |         2E24          |         4E23         |      03       |       01        |        00        |    01    |  31 2C 20  |

However, we need to flip the 2  values for `ElementTimeRemaining` => `4E 23` => `234E`  
`0x234E` = `9038` Which is 9 Seconds.  
Another note : `ElementStance` only has 6 values possible, realistically :  
`0x01`, `0x02`, `0x03` and  
`0xFF`, `0xFE`, `0xFD`. Those values are negative. `0xFD` = `253` = `-3`  
Positive values are for fire stacks, negative values are for ice stacks.  
This happens because `ElementStance` is a `sbyte`: a Signed byte (has a sign, aka `-`)  

and so, we get the regex.  
`\[.{14}1F:[A-F0-9]{8}:[a-zA-Z-' ]{3,21}:(?<elemTimer2>[A-F0-9]{0,2}?)(?<PolyTimer>[A-F0-9]{0,4}?)19:(?<polyglotStacks>[A-F0-9]{0,2}?)(?<umbralHearts>[A-F0-9]{0,2}?)(?<ElemStacks>[A-F0-9]{0,2}?)(?<elemTimer1>[A-F0-9]{0,2}?):.{0,6}?(?<enoState>01)?:`  
Quite a handful isn't it.

Now, do keep in mind that our `ElementTimeRemaining` is split in 2, so we'll have to combine both inside the trigger. Quite simple, as you can just reference it like so:
`${elemTimer1}${elemTimer2}`  

[Here is an example trigger for BLM Gauge](https://raw.githubusercontent.com/Aho-Senpai/Aho-Triggers/main/Triggernometry/Docs/resources/BLM_Gauge_Example.xml)  
[How to import](#how-do-i-addimport-triggers-not-repos-)  
(Note: You will need at least Triggernometry version BETA: `Triggernometry_1_1_4_0_b2` for this trigger to work properly)  
(TO DO: Change note when version is out of beta)

# Thanks

Thanks to anyone that helped in one way or another in making this Doc  

For already existing documentation:  
quisquous (Paprika#0793) [Cactbot](https://github.com/quisquous/cactbot) Docs  
goat (goat#0909) [Dalamud](https://github.com/goatcorp/Dalamud) Docs  
Thanks to anyone else involved in said documentations of course ^^

For providing Logs:  
Zeffuro (Zeffuro#3033)  
Katt (Katt#2773)  
Rykhas Gnokas (Ry#2618)  

For providing good feedback:  
TechnoHunter (TechnoHunter#2706)  
