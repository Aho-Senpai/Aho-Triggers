# HOW TO SETUP UwU TITAN GAOLS  

## Step 1
Make sure both your game's party list sorting and Triggernometry's party sorting matches.  
Where do you find those ?  
- Game : 
    - System (ESC Menu if on keyboard, or Options if on controller)  
    - Character Configuration  
    - UI Settings  
    - Party List > Party List Sorting
        - (Role Sort Settings if you changed the defaults)  

![gamePartyListSettings](https://raw.githubusercontent.com/Aho-Senpai/Trigg-Aho-Repos/main/Triggernomety/README/READMEs%20Resources/UwU-Gaols-PlayerMark/gamePartyListSettings.PNG)
  
- Triggernometry : 
    - Triggernometry plugin tab in ACT
    - Top right > Options
    - Edit Config
    - Final Fantasy XIV Tab
    - Party List Odering

![TriggPartyListSettings](https://raw.githubusercontent.com/Aho-Senpai/Trigg-Aho-Repos/main/Triggernomety/README/READMEs%20Resources/UwU-Gaols-PlayerMark/TriggPartyListSettings.PNG)

### MAKE SURE BOTH MATCHES !

## Step 2
Edit `Gaols Priority List` Trigger if you want to change the order players get marked. For example, if you want the Player 4 in your partylist to be marker first, then move it at the top. (Use the Move UP/Down buttons to do so)  
![MarkPriority](https://raw.githubusercontent.com/Aho-Senpai/Trigg-Aho-Repos/main/Triggernomety/README/READMEs%20Resources/UwU-Gaols-PlayerMark/PlayerOrder.PNG)

## Step 3
Make in-game macros to mark players. You should end up with 9 macros : one for each player, and one that removes all the marks.  
so macro 1 would be `/mk attack <1>`  
then macro 2 would be `/mk attack <2>`  
then macro 3 `/mk attack <3>`  
and so on until macro 8 `/mk attack <8>`  
Then, macro 9 will be  
```
/merror off
/mk clear <1>
/mk clear <2>
/mk clear <3>
/mk clear <4>
/mk clear <5>
/mk clear <6>
/mk clear <7>
/mk clear <8>
```
![ingameMacro1](https://raw.githubusercontent.com/Aho-Senpai/Trigg-Aho-Repos/main/Triggernomety/README/READMEs%20Resources/UwU-Gaols-PlayerMark/ingame-macros1.PNG)  
![ingameMacro2](https://raw.githubusercontent.com/Aho-Senpai/Trigg-Aho-Repos/main/Triggernomety/README/READMEs%20Resources/UwU-Gaols-PlayerMark/ingame-macro2.PNG)  
![ingameMacro3](https://raw.githubusercontent.com/Aho-Senpai/Trigg-Aho-Repos/main/Triggernomety/README/READMEs%20Resources/UwU-Gaols-PlayerMark/ingame-macros3.PNG)

## Step 4
Change keybinds if you want to use other keys than F1-F9  
WARNING: Modifiers-Keys (Shift+A for example) tend to get ignored by the game as well as numpad, so you kinda have to stick to regular keys.  
Here's the link if you need to lookup the keycodes  
https://msdn.microsoft.com/en-us/library/system.windows.forms.sendkeys.send.aspx
![keybindsChange](https://raw.githubusercontent.com/Aho-Senpai/Trigg-Aho-Repos/main/Triggernomety/README/READMEs%20Resources/UwU-Gaols-PlayerMark/keybinds.PNG)


## Step 5
Place your Macros on a hotbar with the keybinds assigned to it. (I will not explain how to do that, i *really* hope you do know how to do at least that much before going into an ultimate fight)  
OFC make sure you place macro 1 on F1 and so on (assuming you kept default binds)

## YOU ARE DONE !  
  
  
## Troubleshooting :   
- I have a big red text flashing in the middle of my screen for 5 seconds when gaols happen, how do i remove that ?
    - This means there is an issue and the List is more than 3 players. It should NOT happen. If it does, please ping me or DM me on discord about it.  
- I have another issue !
    - Ping me or DM me on Discord!  


## Contact : 
- Triggernometry Discord (Why aren't you in there already =P) : https://discord.gg/6f9MY55
- Myself : `Aho Senpai#0818`

## Thanks
Thanks to Illidra on Discord for making the original triggers and explaining how it worked (it's always a bit confusing to look at someone else's work)
