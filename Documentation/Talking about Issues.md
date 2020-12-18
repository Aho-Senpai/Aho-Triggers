## Regex-ing Buffs

`1[AE]:[A-F0-9]{8}:(?<target>[a-zA-Z-' ]{3,21}) (?>gains|loses) the effect of Regen from (?<caster>[a-zA-Z-' ]{3,21})(?> for (?<timer>\d{1,2})\.\d{1,2} Seconds)?\.`  

Here, the main issue is that the regex is almost identical to say, Dia  
`1[AE]:[A-F0-9]{8}:(?<target>[a-zA-Z-' ]{3,21}) (?>gains|loses) the effect of Dia from (?<caster>[a-zA-Z-' ]{3,21})(?> for (?<timer>\d{1,2})\.\d{1,2} Seconds)?\.`  
Plus, it's harder to make the regex works on various languages, mainly because there is no SkillID

HOWEVER

the Skill Used log lines does not have the duration  
`15:[A-F0-9]{8}:(?<caster>[a-zA-Z-' ]{3,23}):89:Regen:[A-F0-9]{8}:(?<target>[a-zA-Z-' ]{3,21}):`

So, in this case what's the best option ?  
Regex off of the `1[AE]:` line ? or off of the `15:` line ?  
To that i do not have the answer, it mainly depends on what you want to achieve really. The easier way would be going for the buff line, mainly because you do have access to the duration. However, it's possible to go for the skill used and set a duration manually. It's up to YOU

Another thing to consider however, is the timers. often the buff will take 0.5s or so to show up, which isalso why a lot of people will prefer triggering off of the buff line to be more accurate with the game timers

From NGLD : "The network version for the 1[AE] lines has the buff ID. That should make language agnostic triggers easier."
