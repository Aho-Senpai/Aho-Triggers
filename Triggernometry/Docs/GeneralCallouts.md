# General Callouts : About

<!-- TODO & Guidelines WIP

- Trigger Names : "Boss# - <Callout> - <MechanicName>"
- Custom Callout (for callouts that only happen in 1 dungeon or specific instance) : "Boss# - CUSTOM - <MechanicName>"
- "Boss# - NO_CALLOUTS - <MechanicName/Description>" in case of logic only triggers, or any trigger that doesn't have TTS

- For example, "Go East" must always refer to "east of the arena", as opposed to "go right" must be "right of the boss" (or relevant Mob of mechanic at the time)  
- In cases like "go east", the callout is calling out the safe side, not the side the boss is hitting.



-->

# Setting Up :

IF nothing is done, it will default to English callouts.

Otherwise : `/e AhoTTSCalloutsLang=EN` in-game 

(Replace `EN` with your language)  
(`EN` をあなたの言語に置き換えてください)  
(Remplacez `EN` par votre langue)  
(Vervang `EN` door uw taal)  
(将`EN`替换为您的语言)  
(`EN`을 귀하의 언어로 대체)  
(Substitua `EN` pelo seu idioma)  

Languages Availble :

EN : English  
JP : 日本語  
FR : Français  
DE : Deutsch  
CN : 中文   
KR : 한국어  
PT : Português  

<!--
# About Callouts :

# Adding Translations
-->
<!-- 
## Examples
Example AoE Trigger :
```xml
<?xml version="1.0"?>
<TriggernometryExport Version="1">
  <ExportedTrigger Enabled="true" Source="FFXIVNetwork" Name="Boss1 - AoE - Path of Light" Id="6b017693-ba41-445f-af29-268379be816b" RegularExpression="^20\|[^|]*\|[^|]*\|[^|]*\|3DC5\|">
    <Actions>
      <Action OrderNumber="1" TextAuraFontSize="8.25" TextAuraFontName="Microsoft Sans Serif" TriggerId="54d17c9d-1f51-4275-8c4c-f40e6fd99675" TriggerForce="regexp" ActionType="Trigger">
        <Condition Enabled="false" Grouping="Or" />
      </Action>
    </Actions>
    <Condition Enabled="false" Grouping="Or" />
    <Conditions />
  </ExportedTrigger>
</TriggernometryExport>
```

Example CUSTOM callout trigger
```xml
<?xml version="1.0"?>
<TriggernometryExport Version="1">
  <ExportedTrigger Enabled="true" Source="FFXIVNetwork" Name="Boss2 - CUSTOM - Chyme Spawn : Kill" Id="44250230-8094-4f82-8209-5611ed16c73c" RegularExpression="^03\|[^|]*\|[^|]*\|[^|]*\|[^|]*\|[^|]*\|[^|]*\|[^|]*\|[^|]*\|3794\|3730\|">
    <Actions>
      <Action OrderNumber="1" UseTTSTextExpression="Kill the Chyme" TextAuraFontSize="8.25" TextAuraFontName="Microsoft Sans Serif" ActionType="UseTTS">
        <Condition Enabled="true" Grouping="Or">
          <ConditionSingle Enabled="true" ExpressionL="${pvar:AhoTTSCalloutsLang}" ExpressionTypeL="String" ExpressionR="EN" ExpressionTypeR="String" ConditionType="StringEqualCase" />
          <ConditionSingle Enabled="true" ExpressionL="${epvar:AhoTTSCalloutsLang}" ExpressionTypeL="Numeric" ExpressionR="0" ExpressionTypeR="Numeric" ConditionType="NumericEqual" />
        </Condition>
      </Action>
      <Action OrderNumber="2" UseTTSTextExpression="Mate Chyme rápido" TextAuraFontSize="8.25" TextAuraFontName="Microsoft Sans Serif" ActionType="UseTTS">
        <Condition Enabled="true" Grouping="Or">
          <ConditionSingle Enabled="true" ExpressionL="${pvar:AhoTTSCalloutsLang}" ExpressionTypeL="String" ExpressionR="PT" ExpressionTypeR="String" ConditionType="StringEqualCase" />
        </Condition>
      </Action>
    </Actions>
    <Condition Enabled="false" Grouping="Or" />
    <Conditions />
  </ExportedTrigger>
</TriggernometryExport>
```

Example trigger General Callout:
```xml
<?xml version="1.0"?>
<TriggernometryExport Version="1">
  <ExportedTrigger Enabled="true" Source="None" Name="AoE" Id="54d17c9d-1f51-4275-8c4c-f40e6fd99675" RegularExpression="">
    <Actions>
      <Action OrderNumber="1" UseTTSTextExpression="AoE" TextAuraFontSize="8.25" TextAuraFontName="Microsoft Sans Serif" ActionType="UseTTS">
        <Condition Enabled="true" Grouping="Or">
          <ConditionSingle Enabled="true" ExpressionL="${pvar:AhoTTSCalloutsLang}" ExpressionTypeL="String" ExpressionR="EN" ExpressionTypeR="String" ConditionType="StringEqualCase" />
          <ConditionSingle Enabled="true" ExpressionL="${epvar:AhoTTSCalloutsLang}" ExpressionTypeL="Numeric" ExpressionR="0" ExpressionTypeR="Numeric" ConditionType="NumericEqual" />
        </Condition>
      </Action>
      <Action OrderNumber="2" UseTTSTextExpression="Dano em Área" TextAuraFontSize="8.25" TextAuraFontName="Microsoft Sans Serif" ActionType="UseTTS">
        <Condition Enabled="true" Grouping="Or">
          <ConditionSingle Enabled="true" ExpressionL="${pvar:AhoTTSCalloutsLang}" ExpressionTypeL="String" ExpressionR="PT" ExpressionTypeR="String" ConditionType="StringEqualCase" />
        </Condition>
      </Action>
    </Actions>
    <Condition Enabled="false" Grouping="Or" />
    <Conditions />
  </ExportedTrigger>
</TriggernometryExport>
```
## Templates
Template Trigger for AoE and basic callouts like that :
```xml
<?xml version="1.0"?>
<TriggernometryExport Version="1">
  <ExportedTrigger Enabled="true" Source="FFXIVNetwork" Name="Boss# - <Callout> - <Mechanic>" Id="6b017693-ba41-445f-af29-268379be816b" RegularExpression="^20\|[^|]*\|[^|]*\|[^|]*\|<MechanicID>\|">
    <Actions>
      <Action OrderNumber="1" TextAuraFontSize="8.25" TextAuraFontName="Microsoft Sans Serif" TriggerForce="regexp" ActionType="Trigger">
        <Condition Enabled="false" Grouping="Or" />
      </Action>
    </Actions>
    <Condition Enabled="false" Grouping="Or" />
    <Conditions />
  </ExportedTrigger>
</TriggernometryExport>
```

Template for TB and the like :
```xml
<?xml version="1.0"?>
<TriggernometryExport Version="1">
  <ExportedTrigger Enabled="true" Source="FFXIVNetwork" Name="Boss# - <Callout> - <Mechanic>" Id="cd730eed-998c-4f27-a2df-c332e82387d5" RegularExpression="^20\|[^|]*\|[^|]*\|[^|]*\|<MechanicID>\|[^|]*\|[^|]*\|(?&lt;targetName&gt;[^|]*)\|">
    <Actions>
      <Action OrderNumber="1" TextAuraFontSize="8.25" TextAuraFontName="Microsoft Sans Serif" TriggerText="${targetName}" ActionType="Trigger">
        <Condition Enabled="false" Grouping="Or" />
      </Action>
    </Actions>
    <Condition Enabled="false" Grouping="Or" />
    <Conditions />
  </ExportedTrigger>
</TriggernometryExport>
```
-->
