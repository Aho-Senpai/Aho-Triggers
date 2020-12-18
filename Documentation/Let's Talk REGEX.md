Make sure you do check out [Quisquous Log Guide](https://github.com/quisquous/cactbot/blob/master/docs/LogGuide.md)

Let's talk about REGEX a bit more here
- FFXIV Network Log Lines

```[09:30:53.841] 15:1004594B:Aho Senpai:07:Attack:4000051C:Striking Dummy:710003:6CA0000:0:0:0:0:0:0:0:0:0:0:0:0:0:0:2862500:2862500:0:0:0:1000:718.0647:267.0143:28.31746:-1.570485:93968:93968:10000:0:0:1000:715.9233:265.7539:28.38361:1.40684:00318599```

Here, we can break that line down. First, we don't really care about the time, so we can ignore that for now

`15:1004594B:Aho Senpai:07:Attack:4000051C:Striking Dummy:710003:6CA0000:0:0:0:0:0:0:0:0:0:0:0:0:0:0:2862500:2862500:0:0:0:1000:718.0647:267.0143:28.31746:-1.570485:93968:93968:10000:0:0:1000:715.9233:265.7539:28.38361:1.40684:00318599`

Then, the whole part that starts with `0:0:0:0` and so on, is mostly data we don't care about (if you do, you probably aren't reading this), so we can strip that part too

`15:1004594B:Aho Senpai:07:Attack:4000051C:Striking Dummy:710003:6CA0000:`

Now that we have the part that interest us, let's see what all of this means

15|1004594B|Aho Senpai|07|Attack|4000051C|Striking Dummy|710003|6CA0000|
---|---|---|---|---|---|---|---|---
Line ID|Caster ID|Caster Name|Ability ID|Ability Name|Target ID|Target Name|Flags [ ]*to add link for flags*|Damage

Now that this is clear, let's say i want to make a regex for a trigger to beep everytime i do an AA (Auto Attack)

`15:1004594B:Aho Senpai:07:Attack:`

This part of the line is all i really need, and i can actually remove the Ability Name part if i want too, but it'll leave it. 
(Removing the ability name in this case can really help if trying to make a trigger that work regardless of game language)

Now, While this regex in itself can work, it's far from ideal for a major reason: 
- it's tied to MY character name and ID

The main concern with that is that if i decide to play on another character, it won't work. Or if i try to give my trigger so someone else, it won't work either

In that case, i need to make sure the "variable" elements are REGEX-ed

`15:[A-F0-9]{8}:[a-zA-Z-' ]{3,21}:07:Attack:`

OK. But now the issue is that it will trigger on anyone using a AA
(if you are lost here, i suggest you play around with [Regex101](https://regex101.com/))  
In this case, we have basically 2 options: 
1. - Make a capture group for the Caster ID
2. - Make a capture group for the Caster Name

The main concern of using the Caster Name field is that if you play with someone that has the exact same name as you, it can cause some issues (however, i have yet to see this happen)

`15:[A-F0-9]{8}:(?<player>[a-zA-Z-' ]{3,21}):07:Attack:`

`15:(?<playerid>[A-F0-9]{8}):[a-zA-Z-' ]{3,21}:07:Attack:`

Note that the name of the capture group can be what you want (the name being <name>)

Now that we have our basic regex with what we want to capture, it's time to start thinking about making it a bit more efficient  
See, the issue with the regex we have now is that it will go through each line looking for a string that starts with `15:` basically, which is not ideal. We want our regex to "fail" as soon as possible if the line does not match

Remember how the line starts with the timestamp ? Yeah, we basically keep that in mind in the regex

`\[.{14}15:[A-F0-9]{8}:(?<player>[a-zA-Z-' ]{3,21}):07:Attack:`

The timestamp being static lenght, we can safely do this. this heavily reduce the amount of steps needed to "fail" the regex

There you go, you now have a nice regex for your basic AAs (not super usefull, granted)
