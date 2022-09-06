<h1 style="text-align:center">Regex Basics</h1>  

ok, let's go over the basics of regex, and the groups that are usually used for FFXIV log lines regex  

there are ressources out there if you want to learn more about regex in general, or if this guide is not enough for you  

before we start, i feel the need to mention that when you copy/paste from ACT log or anything else, i often find  the issue where you have an "invisible" newline character at the end of your string, making it so if you do not delete it, your regex WILL NOT WORK. So make sure you watch out for that  

so, le's go over a few basics regex elements to begin with  
`.` will match any single character  
`\d` will match any digit  
`\w` match world characters (is equal to `[a-zA-Z0-9 ]`  
`+` is a quantifier, and will match  or more (is used after a character or a group. for example : `F+XIV` would match the string "FFXIV" but also "FFFXIV" so be careful)  
`?` is another quantifier, will match 0 or 1 of (`FFXI?V` would match "FFXIV" but also "FFXV")  
`*` is yet another quantifier, will match any amount of IMPORTANT : i do not recommend using thi s asa general rule of thumb, unless you know what you do OR there's a couple exeptions where i would use it, will get to that later  
And now, what if we combine some ? yes you can  
`??` will match 0 or 1 as few times as possible (not used a lot, but really handy when you need it for example : `FFX??IV` would match "FFXIV" as well as "FFIV")  
and well, you also have the others (`+?` `*?`) but i have yet to have a situation where i would need them (i do use `.*?` a lot actually, but it is generally for testing purpose)  
`|` is a "or", it'll match either side of it (mostly used in capture groups) of course you can "stack" them to have a multiple option regex like so `(one|two|three|four)` (this is will match "one" or "two" or "three" or "four")  
`\` will "escape" a character you place after and match it literally `\ ` for example will match " " (space) literally. this is mainly used for the "special" characters like `[{(.` and so on  

moving on to groups constructs  
`a-z` will match any letter from "a" to "z"  
`A-Z` is well, the same as above but for capital letters  
`0-9` will match any numbers between 0 and 9 (it's the equivalent of `\d` really)  
`[ ]` will match a set of characters you set it to. for example `[a-zA-Z]` will match any non-digit charater (letters)  
`( )` will make a capture group, the main use is the following  
`(?< > )` will make a named capture group, which you can reference by it's name (for example, `(?<player>ME)` would match "ME" in a string, and you can reference it by the `<player>`)  
`(?> )` will make an atomic group, will is not named and not referencable (pretty handy when needed)  
`{ }` will quantify depending on the values you enter  
`{ , }` will match between the 2 values you enter  

special mention for single character choices (like `(1|2)` or `(1|2|3|4)`)  
keep in mind that in that special case you can simply use `[12]` or `[1234]` and keep your regex simple and clean  

AVOID as much as you can  
`.*` is generally speaking "bad practice" mainly for the fact that it matches anything and has no limit. PLEASE DO NOT USE CARELESSLY  
`.+` is in the same vein really, avoid it just as much  
Starting a regex with a capture group. Avoid avoid avoid  

ok so now with all that, what cool things can we do ?  
well, its mainly gonna depends on what you want your regex to capture  
but lt's go over some commonly used groups and examples for FFXIV regex  

`[A-F0-9]{8}` is mainly gonna be used to regex entities IDs as it's a 8 character HEX  
`(?<player>[a-zA-Z-' ]{3,21})` is mainly used to reference a player by it's name (used a lof if you want to callout that player name for whatever reason) the `{3,21}` here is because of SE's limitations on player name  
`\[.{14}` is used to ignore the timestamp at the begining of ACT log lines (this is the most efficient steps wise i found)  
`(?<timer>\d{1,2}\.\d{1,2})` is usually used to capture a timer, like the duration of a buff or debuff  

of course you can name your capture groups however you want, but it is strongly advised to keep them consistent  
this way your regex are simpler to read, you can go back to it and not have to scratch your head at "how did i do this again?"  
and more people can look at it and instantly understand what that regex do  

now, for a few more special cases  
remember how i said earlier that you should avoid using `.*` as much as possible ? well, while it is true and you should keep that rule, there are a few situations or cases where i's acceptable to use it  
the main cases are if you have "delimiters". for example, in a ACT log `:` is my delimiters, so if i do this `:.*:` it's "ok-ish" because the delimiters stop it  
the other case is when used with a `?` like so `.*?` but it rarely has a use case  
