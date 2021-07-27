# NBTeams Pure Forge 1.12.2 - Docs in progress
An default configuration is automaticaly generated and is fully operational. You will be able to customize it to your servers needs, even the smallest details are configurable, you can for example modify more than 250 messages! **No dependency required** <br>
A brief summary of some of the features:
- Autonomous management of teams by the players
- Private team chats
- Advanced administration tools, Spy, etc...
- Customizable portals and destination
- Simple quest system & Creation (For Developers: You can create your own quests integrated to NBTeams, for more info contact me) (Configuration tools are also available)
- Advanced UI system
- Economy system with currency inflation, exchange rates on multiple currencies
- Leaderboards

Many features are not listed above, however will be included in the documentation below. Furthermore, new features will be added soon! Performance has been greatly improved from the previous sponge version.

## Installation
Add the file "NBTeams.jar" in the mod folder of your server. Then start it. You will then just have to activate your license.

### Licence
You need to execute commands:<br>
```/nbt Licence ServerName <ServerName>```<br>
```/nbt Licence ServerKey <ServerKey>```<br>
```/nbt Licence Connect```<br>
```/nbt Licence IP```<br>
Then send the result of last command to the developper, and it's finished, you can enjoy NBTeams.

### Permissions
There are two types of permissions, the individual ones, specific to each command, or the groups which directly contain pre-made configurations to save you time.

#### Individual
**[Base]**<br>
nbteams.help<br>
nbteams.plugin<br>

**[Player]**<br>
nbteams.info<br>
nbteams.join<br>
nbteams.request<br>
nbteams.leaderboard<br>
nbteams.team_list<br>
nbteams.member_list<br>
nbteams.claim<br>

**[Member]**<br>
nbteams.leave<br>
nbteams.spawn<br>
nbteams.destination<br>
nbteams.chat<br>
nbteams.home<br>

**[Commander]**<br>
nbteams.invite<br>
nbteams.request_list<br>
nbteams.kick<br>
nbteams.refuse<br>
nbteams.accept<br>
nbteams.sethome<br>

**[Leader]**<br>
nbteams.demote<br>
nbteams.promote<br>
nbteams.setlead<br>
nbteams.prefix<br>
nbteams.delete<br>

**[Admin]**<br>
nbteams.licence<br>
nbteams.portal<br>
nbteams.inventory<br>
nbteams.admin<br>
nbteams.bonus<br>
nbteams.setspawn<br>
nbteams.spy<br>
nbteams.points<br>
nbteams.progress<br>

**[Private]**<br>
nbteams.new<br>
nbteams.config<br>

#### Groups
**nbteams.groups.base** -> [Base]<br>
**nbteams.groups.player** -> [Player] + [Member] + [Commander] + [Leader]<br>
**nbteams.groups.admin** -> [Admin]<br>
**nbteams.groups.root** -> [Private]<br>

## Configuration file

> You have many configuration files in NBTeams (14) but you do not have to change them all. Here is a list of descriptions for each of the files with their respective functionality.

### General.json
It is a file with all the main elements of the plugin, the balancing of the teams, the number of quests, the spawn, the prices of creation of the teams, the default menu ect... 

### Messages.json
This is where you will find all the texts of the plugin, which you can adjust as you wish, the colour aliases are available using the "&" symbol. Text aliases are also available using the "{}" symbols, these vary depending on the message. All available aliases are used in the default texts.

### QuestInitializer.json
Allows quests to be automatically initialized after configuration. Note that quests have several different types:
- **Daily** (every day)
- **Donor** (every day)
- **Weekly** (every week)
- **Monthly** (every month)<br>
and each of them has several possible rarities:<br>
- **Common** (50%)
- **Rare** (40%)
- **Legendary** (10%)

You can change the missions and rewards for each category.<br>Rewards can be in-game money, team points, items, or custom command execution. <br>
By default, NBTeams has several types of missions, among which:
- **MINE**
- **CRAFT**
- **CATCH** (Pokemon_Name / Pokemon_Type)
- **EVOLVE** (Pokemon_Name / Pokemon_Type)
- **HATCH** (Pokemon_Name / Pokemon_Type)
- **PICK** (Apricorn / Berries)
- **DEFEAT** (Pokemon_Name / Pokemon_Type / TrainerName)<br>
You can create others as long as they are declared.
To ignore a mission type in the configuration add a "!" before the name. Example: "MINE": { ... } can be chosen, but "!PICK": { ... } cannot be chosen. The formats will be detailed later in this document.

### Formats.json

### Economy.json

### UI.json

### Destination.json

### Licence.json

----

## Configuration

### Portal and destinations

### UI

### Quest system

### Economy system

### Command interpreter  

### NPC interaction

### Are you developper ?
Several APIs are available, contact me for more information, a dedicated section will be created in the wiki. 

# Licensed server
*Have you found a server that uses NBTeams without permission? Contact me quickly.*<br><br>
**Forge version**: None<br>
**Sponge version**: Frontier Pixelmon, Miner.GG, PokeHills, PixelmonCraft<br>
**Deprecated version**: Livadia<br>
