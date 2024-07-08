# Let's Talk Regex

Make sure you do check out [Quisquous Log Guide](https://github.com/OverlayPlugin/cactbot/blob/main/docs/LogGuide.md)

Here, we have 2 choices : Either use "ACT-Formatted" log lines (fields are `:` separated), or use "Raw Network Lines" (fields are `|` formatted).  

While the raw network lines can be a bit harder to read if you are getting your feets wet, they are more reliable, almost never change, and usually contain more information.  

We will thus be using the raw network lines from here on out.  


## FFXIV Network Log Lines

### Where do I get them from?

By default, from `C:\Users\<USER>\AppData\Roaming\Advanced Combat Tracker\FFXIVLogs`.  
Sort by `Date modified` and open the most recent file.  
I personally recommend you use a text editor such as VSCode to open them, as it has a lot of features and tools that can make your job of looking through the log easier. 

- "But wait, I don't have anything on that location?"  
In that case, open ACT and look : `ACT > Plugins > FFXIV ACT Plugin > 'Output Log File Location'`. You can even click on "Open Output Log Folder" button from there. 

### Analysis

First, let's see we have ... let's take a simple `Auto Attack` line to start with. The goal here will be to make a simple RegEx for it.  
```
21|2022-05-13T10:13:38.4740000+11:00|1022660B|Aho Senpai|07|attack|4000082D|Striking Dummy|710003|2470000|0|0|0|0|0|0|0|0|0|0|0|0|0|0|44|44|0|10000|||-602.87|-860.82|32.09|-2.36|43601|43601|10000|10000|||-601.29|-859.55|30.08|-2.42|0000B11E|0|1|a9039149047b7e87
```
Looks scary? Worry not. We can and will break it down.  

Again, don't hesitate to reference [Quisquous Log Guide](https://github.com/OverlayPlugin/cactbot/blob/main/docs/LogGuide.md). It has a Table Of Contents at the top.  

How does that help? Well, Network lines have the LineID as the first field of the line. `21` in this case. So, combined with the log guide from above, we can easily check that specific line structure : https://github.com/quisquous/cactbot/blob/main/docs/LogGuide.md#line-21-0x15-networkability (If the link doesn't scroll to the correct place, try refreshing the page, and/or manually scrolling to it. Or, scroll all the way to the top and click on the correct link again.)  

```
21|[timestamp]|[sourceId]|[source]|[id]|[ability]|[targetId]|[target]|[flags]|[damage]|[?]|[?]|[?]|[?]|[?]|[?]|[?]|[?]|[?]|[?]|[?]|[?]|[?]|[?]|[targetCurrentHp]|[targetMaxHp]|[targetCurrentMp]|[targetMaxMp]|[?]|[?]|[targetX]|[targetY]|[targetZ]|[targetHeading]|[currentHp]|[maxHp]|[currentMp]|[maxMp]|[?]|[?]|[x]|[y]|[z]|[heading]|[sequence]|[targetIndex]|[targetCount]
```

But wait, it's missing something ! Yes, the weird hash at the end of the line. We can ignore it entirely. It's the FFLOGS hash, we do not need it.  
We can also regex out the `timestamp`, as it's unlikely you'll need it. To do that, we simply "skip" over that field with `[^|]*`. Read my [Basic Regex Talk](https://github.com/Aho-Senpai/Aho-Triggers/blob/main/Documentation/Basic%20REGEX%20talk.md) if you are lost here.  

```
21|[^|]*|1022660B|Aho Senpai|07|attack|4000082D|Striking Dummy|710003|2470000|0|0|0|0|0|0|0|0|0|0|0|0|0|0|44|44|0|10000|||-602.87|-860.82|32.09|-2.36|43601|43601|10000|10000|||-601.29|-859.55|30.08|-2.42|0000B11E|0|1
```  
Ok, so that's the Log Line structure. Now, let's trim some of the info we don't need.  
```
21|[^|]*|1022660B|Aho Senpai|07|attack|4000082D|Striking Dummy|710003|2470000|
```
Ok, seems a bit less daunting doesn't it? But there's still a few things we can remove. Here we are only trying to make a regex for an attack. We don't care hoc much damage or what target it landed on.  
```
21|[^|]*|1022660B|Aho Senpai|07|attack|
```
Ok, is that good enough now? Yes. Almost. We can also remove the `attack` field, as it'll make the regex work regardless of the user game language setting here.  
While we are at it, let's also not forget to use a `^` at the begining of the regex, to make sure we start the regex at the start of the line. It also helps make the regex faster.
```
^21|[^|]*|1022660B|Aho Senpai|07|
```
Ok, that looks simple enough right? However, we can go deeper. This regex will ONLY work for ME. It has my name and ID hardcoded in there afterall.  
How do we deal with that? Well, here comes capture groups.  
```
^21|[^|]*|[^|]*|(?<playerName>[^|]*)|07|
```
Ok, but what do i do with this? Well, you'll have to access a capture group and compare it with what you want it to match. `${playerNamme}`  

There you go, you now have a nice regex for your basic AAs (not super usefull, granted)
