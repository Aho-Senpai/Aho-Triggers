<h1 style="text-align:center">Logs Regex</h1>

<h2>Table of Contents</h2>

- [Network Logs](#network-logs)
  - [Add/Remove Combatant : 03/04](#addremove-combatant--0304)
  - [StartCasting : 20](#startcasting--20)
  - [NetworkDeath : 25](#networkdeath--25)
  - [NetworkBuffGain : 26](#networkbuffgain--26)
    - [26: BuffStacks](#26-buffstacks)
  - [NetworkBuffLoss : 30](#networkbuffloss--30)
- [Encounter Logs](#encounter-logs)

# Network Logs

```
20|0000-00-00T00:00:00.0000000+00:00|00000000|Player Name|05|Teleport|00000000|Player Name|5.00||60e3acaf4f1e8af4a9cd32ae876521ea
```

Here's a few things that are gonna be the same on all lines : 
| Line ID |             Timestamp             |                                 Data                                 |           FFLogs Hash            |
| :-----: | :-------------------------------: | :------------------------------------------------------------------: | :------------------------------: |
|   20    | 0000-00-00T00:00:00.0000000+00:00 | \|00000000\|Player Name\|05\|Teleport\|00000000\|Player Name\|5.00\| | 60e3acaf4f1e8af4a9cd32ae876521ea |


## Add/Remove Combatant : 03/04

```
^03\|[^|]+\|(?<id>[^|]+)\|(?<name>[^|]+)?\|(?<jobID>[^|]+)\|(?<level>[^|]+)\|(?<petOwnerID>[^|]+)\|(?<worldID>[^|]+)\|(?<worldName>[^|]+)?\|(?<bnpcName>[^|]+)\|(?<bnpcBase>[^|]+)\|(?<currentHP>[^|]+)\|(?<maxHP>[^|]+)\|(?<currentMP>[^|]+)\|(?<maxMP>[^|]+)\|(?<currentTP>[^|]+)\|(?<maxTP>[^|]+)\|(?<xPos>[^|]+)\|(?<zPos>[^|]+)\|(?<yPos>[^|]+)\|(?<heading>[^|]+)\|
```
`level` is in HEX so : `0x50` = `80` for example.  
`worldName` will be empty is `worldID` is `0`  
`name` can be empty for some entities.  
`bnpcName` and `bnpcBase` are entity model nameID and ID. For example, a training dummy can have different models.  

(you will need to change the `03` to `04` in the regex if you need to use that line, other than that it's the same format)

## StartCasting : 20

```
20|2021-02-20T17:29:36.9520000+01:00|1051BFF8|Zeffuro Jugo|05|Teleport|1051BFF8|Zeffuro Jugo|5.00||60e3acaf4f1e8af4a9cd32ae876521ea
20|2021-02-20T17:33:33.6220000+01:00|1051BFF8|Zeffuro Jugo|1D3F|Midare Setsugekka|400003EB|Striking Dummy|1.30||381ef764da00eb6df97e7ca6c1362bf5
20|2021-02-20T17:33:51.4470000+01:00|1051BFF8|Zeffuro Jugo|1D41|Higanbana|400003EB|Striking Dummy|1.30||aeefd3cf52bb387d511fdadc41282d94
20|2021-02-20T17:34:41.3200000+01:00|1051BFF8|Zeffuro Jugo|1D3F|Midare Setsugekka|400003EB|Striking Dummy|1.30||a8fca70ae398d38a334b448d92c85682
20|2021-02-20T17:35:18.4050000+01:00|1051BFF8|Zeffuro Jugo|4340|Summon Selene|1051BFF8|Zeffuro Jugo|2.42||f75859368c1c77a48a688c48ee1d993c
20|2021-02-20T17:35:24.1040000+01:00|1051BFF8|Zeffuro Jugo|409D|Broil III|400003EB|Striking Dummy|2.42||1c3012c022244f3d89c60513d203ce3b
20|2021-02-20T16:25:28.8710000+00:00|1064ABA5|Katt Amariyo|05|Teleport|1064ABA5|Katt Amariyo|5.00||e4b56e55e0e025372f3eafad653b5c23
20|2021-02-20T16:32:50.6870000+00:00|1064ABA5|Katt Amariyo|409D|Broil III|40000B75|Striking Dummy|2.41||16dc5b44d4b73c3c7525e69d30e38cab
20|2021-02-20T16:32:55.5890000+00:00|1064ABA5|Katt Amariyo|4340|Summon Selene|1064ABA5|Katt Amariyo|2.41||323f34a0b7d189fec350d4f3f6bd9309
20|2021-02-20T16:32:58.1270000+00:00|1064ABA5|Katt Amariyo|409D|Broil III|40000B75|Striking Dummy|2.41||677808b17079fbe7b4c139afb691ebba
```
| Caster ID | Caster Name | Cast ID | Cast Name | Target ID | Target Name | Cast Duration |
| :-------: | :---------: | :-----: | :-------: | :-------: | :---------: | :-----------: |
| 00000000  | Player Name |   05    | Teleport  | 00000000  | Player Name |     5.00      |
```
^20\|.{33}\|(?<casterID>[A-F0-9]{8})\|(?<casterName>[^\|]{3,21})\|(?<castID>[A-F0-9]+)\|(?<castName>[^\|]+)\|(?<targetID>[A-F0-9]{8})\|(?<targetName>[^\|]+)\|(?<castDuration>[\d]+\.[\d]+)\|
```

## NetworkDeath : 25

```
25|0000-00-00T00:00:00.0000000+00:00|00000000|Player Name|00000000|Player Name||7b1e16ac1e665aadf56cbb67e62a6b29
```

| Dead ID  |  Dead Name  | Killer ID | Killer Name |
| :------: | :---------: | :-------: | :---------: |
| 00000000 | Player Name | 00000000  | Player Name |

```
^25\|.{33}\|(?<deadID>[^\|]{8})\|(?<deadName>[^\|]+)\|(?<killerID>[^\|]+)\|(?<killerName>[^\|]+)?\|
```

Note: `killerName` can be absent, in case `killerID` is `E0000000` (guessing this is the ID for "environemental")  
`deadName` can also be absent, but on a sample size of almost 60k lines it was only the case if `killerID` was `E0000000`, and said entities also had no names on previous log lines, thus it should be safe to ignore those.  

## NetworkBuffGain : 26

```
26|2021-02-20T17:29:22.9660000+01:00|2d|Crafter's Grace|60889.31|10715E97|Morasha Zervishe|10715E97|Morasha Zervishe|46|1571|1571||6f1e2f9446333bbc6876b680935c0f00
26|2021-02-20T17:29:39.8910000+01:00|84d|Aetherial Mimicry: Dps|9999.00|10742955|Hime Tsukishiro|10742955|Hime Tsukishiro|00|43657|43657||17a247580dbaf998c9f0632352614c7a
26|2021-02-20T17:29:39.8910000+01:00|84d|Aetherial Mimicry: Dps|9999.00|106C5252|Alexis Seralia|106C5252|Alexis Seralia|00|43863|43863||1e64810aafb981a101a9ceb4da56ccaf
26|2021-02-20T17:30:08.2440000+01:00|7d|Raging Strikes|20.00|1051BFF8|Zeffuro Jugo|1051BFF8|Zeffuro Jugo|00|106766|106766||745b87da151cffaacad271a0712e9038
26|2021-02-20T17:30:08.3800000+01:00|7a|Straight Shot Ready|10.00|1051BFF8|Zeffuro Jugo|1051BFF8|Zeffuro Jugo|00|106766|106766||70c4de19632d4aeab14623dfa2c027f6
26|2021-02-20T17:30:09.6690000+01:00|4b1|Stormbite|30.00|1051BFF8|Zeffuro Jugo|400003EB|Striking Dummy|28|7400000|106766||3013f9974c98f1995ed9851c95d893ba
26|2021-02-20T17:30:12.1610000+01:00|4b0|Caustic Bite|30.00|1051BFF8|Zeffuro Jugo|400003EB|Striking Dummy|28|7400000|106766||fc150c1767bbf22c1c0d9626ad00b252
26|2021-02-20T17:30:19.1170000+01:00|80|Barrage|10.00|1051BFF8|Zeffuro Jugo|1051BFF8|Zeffuro Jugo|00|106766|106766||a2af2642cf9845afa132e91d6c12b2e8
26|2021-02-20T17:42:00.9850000+01:00|130|Aetherflow|9999.00|1051BFF8|Zeffuro Jugo|1051BFF8|Zeffuro Jugo|01|70522|70522||9abe27adc84951cd7183faf319a89026
26|2021-02-20T17:42:01.0730000+01:00|4bc|Further Ruin|9999.00|1051BFF8|Zeffuro Jugo|1051BFF8|Zeffuro Jugo|01|70522|70522||4bf2d0bd5a7a722f03d087089846af5e
26|2021-02-20T17:42:02.3650000+01:00|7ac|Summon Order II|30.00|40006374|Ifrit-Egi|40006374|Ifrit-Egi|01|70324|70324||05679e111619ef97e528cbc5d1b73e64
26|2021-02-20T17:42:03.5700000+01:00|4bc|Further Ruin|9999.00|1051BFF8|Zeffuro Jugo|1051BFF8|Zeffuro Jugo|02|70522|70522||ffbaa31e1d9da6d3c2c65075046fca6b
26|2021-02-20T17:42:04.1930000+01:00|4bc|Further Ruin|9999.00|1051BFF8|Zeffuro Jugo|1051BFF8|Zeffuro Jugo|01|70522|70522||20cd512df39e1f92bfdea5f953a5ca53
26|2021-02-20T17:42:12.1740000+01:00|7ad|Summon Order III|30.00|400003EB|Striking Dummy|40006374|Ifrit-Egi|01|70324|7400000||6a6416075c200f424177690e8d5073a1
26|2021-02-20T17:42:13.1550000+01:00|13a|Inferno|15.00|40006374|Ifrit-Egi|400003EB|Striking Dummy|00|7400000|70324||724e7b5fd474f6911bc860b9915f3856
```
| Buff ID |   Buff Name    | Buff Duration | Caster ID | Caster Name | Target ID | Target Name | [BuffStack](#26-buffstacks) | Target Max HP | Caster Max HP |
| :-----: | :------------: | :-----------: | :-------: | :---------: | :-------: | :---------: | :-------------------------: | :-----------: | :-----------: |
|   7d    | Raging Strikes |     20.00     | 00000000  | Player Name | 00000000  | Player Name |             00              |    106766     |    106766     |
```
^26\|.{33}\|(?<buffID>[^\|]+)\|(?<buffName>[^\|]+)\|(?<buffDuration>[^\|]+)\|(?<casterID>[^\|]+)\|(?<casterName>[^\|]+)\|(?<targetID>[^\|]+)\|(?<targetName>[^\|]+)\|(?<buffStack>[^\|]+)\|(?<targetMaxHP>[^\|]+)\|(?<casterMaxHP>[^\|]+)\|
```
### 26: BuffStacks

DISCLAIMER: This looks like BuffStacks (Aetherflow starting at 03 and going down) but it also looks like there are some masks or flags as well (meditate having a `1438` for example)

## NetworkBuffLoss : 30

Same Structure as [NetworkBuffGain](#networkbuffgain--26) it looks like

# Encounter Logs