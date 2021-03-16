<h1 style="text-align:center; color:yellow">README</h1>  

## HOW TO INSTALL ?  

### Step 1  

Download the [file](Raid%20Buffs.xml).

### Step 2

Import the file  
![Import Picture](README%20Resources/ACT%20Import.PNG)

### Step 3

Tab back to `Custom Triggers` tab and enjoy your newly imported triggers  
  
## "Limitations"
Those triggers WILL callout all the raidbuffs casted by anyone you happen to "parse" by ACT. This includes players outside of your party/Alliance as well. The only "fix" for this, as far as i'm aware, is to switch your FFXIV Parse Filter to `Party` or `Alliance`.  
Or, you can use plugins that have conditionals, like Triggernometry, Cactbot, SPESPE, ...  

  
## HOW DOES THIS WORKS ?

### REGEX : 
Let's take Trick Attack as an example:  
`(?#-- Trick Attack --)\A1[56]:[A-F0-9]{8}:[^:]*:8D2:(?<name>[^:]*):`  

First, let's ignore the first part `(?#-- Trick Attack --)` as it's a [comment](https://en.wikipedia.org/wiki/Comment_(computer_programming))  

So, we are left with the "actual" REGEX :  
`\A1[56]:[A-F0-9]{8}:[^:]*:8D2:(?<name>[^:]*):`  
Now, Time to break it down into parts:  
| `\A` | `1[56]` | `[A-F0-9]{8}` | `[^:]*` | `8D2` | `(?<name>[^:]*)` |
| ---- | ------- | ------------- | ------- | ----- | ---------------- |

`\A` : is ensuring us that it's only gonna match the start of the line, it's mainly to make the REGEX faster and more efficient  

Honnestly, i wanted to break it down further, but you should go read my other REGEX documentation (plan to break the regex down more here, later)  
[If you don't know what REGEX is](../Documentation/Basic%20REGEX%20talk.md)  
[If you want to learn about FFXIV REGEX](../Documentation/Let's%20Talk%20REGEX.md)  
[Structure of FFXIV LogLines by quisqeous](https://github.com/quisquous/cactbot/blob/master/docs/LogGuide.md)  

## I HAVE MORE QUESTIONS !

Contact me!

Ping me on the [ACT Discord](https://discord.gg/ahFKcmx)  
DM me on Discord : `Aho Senpai#0818`

## Thanks

Thanks to EQAditu for making ACT maintaining it all this time, as well as for his amazing support when asked help <3
