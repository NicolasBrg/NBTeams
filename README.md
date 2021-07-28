# NBTeams Pure Forge 1.12.2 - Version PureForge_1.21.6.b
An default configuration is automaticaly generated and is fully operational. You will be able to customize it to your servers needs, even the smallest details are configurable, you can for example modify more than 250 messages! **No dependency required**<br>
A brief summary of some of the features:
- Autonomous management of teams by the players
- Private team chats
- Advanced administration tools, Spy, etc...
- Customizable portals and destination
- Simple quest system & Creation (For Developers: You can create your own quests integrated to NBTeams, for more info contact me) (Configuration tools are also available)
- Advanced UI system
- Economy system with currency inflation, exchange rates on multiple currencies
- Leaderboards

Many features are not listed above, however will be included in the documentation below. Furthermore, new features will be added soon! Performance has been greatly improved from the previous sponge version. **The plugin uses player UUIDs to avoid losing data if your players change their nickname.**

You can use Tab auto-completion for all plugin commands. The alias for NBTeams is "/nbt" but you can use "/teams" or "/team".

## Installation
Add the file "NBTeams.jar" in the mod folder of your server. Then start it. You will then just have to activate your license.

### Licence
You need to execute commands:<br>
```/nbt Licence ServerName <ServerName>```<br>
```/nbt Licence ServerKey <ServerKey>```<br>
```/nbt Licence Connect```<br>
```/nbt Licence IP```<br>
Then send the result of last command to the developper, and it's finished, you can enjoy NBTeams.

### Permissions & Usages
There are two types of permissions, the individual ones, specific to each command, or the groups which directly contain pre-made configurations to save you time.
You can find the details by following this link: https://github.com/NicolasBrg/NBTeams/wiki/Permission
The uses of the different commands are detailed in the wiki.

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

And each of them has several possible rarities:<br>

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
You have 5 format categories available:
- **Chat**: To manage the displays in the general / private team chat and the different hovers and aliases :)
- **ForbiddenPrefix**: Forbidden aliases when selecting team prefixes in the chat.
- **PrefixBannedWords**: List of forbidden words in team prefixes, to prevent admins from impersonating each other in the chat.
- **QuestElementNickname**: Define prefixes for quests, to avoid seeing the ID of earned items. For example, the item "minecraft:beef" will be displayed in light red "Beef" (default setting). As well as the type "Water" which will be displayed in blue. Gift commands can be displayed differently, for example the command "say This quest will be executed by server!" will be displayed in light blue "A little message in the chat", you can change this to e.g. set up ranks to be won or other effects.
- **LuckPermCommands**: For servers that don't want NBTeams managed prefixes, you can manage server commands here to handle LuckPerm aliases.

### Economy.json
You will find a list of default currencies, the "NBC" and the "PokeDollar", you can create new currencies. For each of them you can change their display name. The interest when using the interest command, and the transition cost from one currency to another, in the default configuration, 1 NBC (for NBCoin) equals 95 PokeDollar. You can change the command of the economy system to "nbecon", the default currency, and have the balance list for each currency for your players.

### UI.json
This file allows you to create as many menus as you want, you can choose particular permissions or change the display name. To create a menu you must use a DeclarationString, which is an array of strings. You will use a series of letters as identifiers for items that you can create in the **Items** category of your menu. An item must at least have the **Type** attribute containing the ID of an item, you can use "Quantity" for the quantity, "PlayerHead" to have the name of a player, "Lore" to add a description, "Enchanted" for the enchanted effect, "Meta" for the block variations, and "Commands" which can add several behaviors to your buttons, you can for example execute actions for:
- LeftClick
- RightClick
- WheelClick
- OutsideUI
- DoubleClick
- ShiftLeftClick
- ShiftRightClick 

The commands executed have aliases "CLOSE" and "BACK" to close the menu or return to the previous menu. To open a menu, you need to use for example the command ``"!nbt Inventory Name {PLAYER}"``. You can use the object marked "\*" which allows you to add actions outside the menu, mainly the "OutsideUI".

For descriptions, you can automatically add quest information using the format "**{Quest_TYPE}#ID**".
For example "**{Quest_Daily}#0**" which will display the first quest of type daily.<br>
![image](https://user-images.githubusercontent.com/30299182/127340028-73526dd0-444f-448b-831d-6341d54baefc.png)


### Destination.json
Each destination has a name, a display name, permissions, criteria for unlocking them, along with the display, your team ranking, personal points, team points (obtainable through quests), the destination (with world and coordinates), the portal, along with the trigger block, the size of the portal and the location, all of which are configurable in game except for the display name, the permission and the required criteria.

----

## Configuration

### Portal and destinations
To create a new destination, simply navigate to the desired coordinates and use the
```/nbt Destination Create NAME``` command. Then design the portal you want, no matter what shape it is, enter it and use the command ```/nbt Portal Name Create {SIZE}```, you will then be teleported. Keep in mind that you need to have permission to pass the portal to create it, so you don't have to worry about it, administrators should have the "nbteams.location.\*" permission. You can also get portal info or remove it with repectively arguments "Info" and "Remove" instead of "Create".

![image](https://user-images.githubusercontent.com/30299182/127337647-93f5fd6c-1d98-4dca-af20-46fc2880b51f.png)
![image](https://user-images.githubusercontent.com/30299182/127337962-73050317-89a2-46ca-ada5-435eebf18060.png)

### UI
To use the menus (for administrators or server commands) you have access to the syntax:
```/nbt Inventory NAME PLAYER``` <br>
- **NAME** : The name of the inventory, you can also use the aliases "**BACK**" or "**CLOSE**", to return to the last menu or close it
- **PLAYER** : The targeted player, if left empty, the inventory will open for you.

### Quest system
Quests are automatically generated using the **QuestInitializer** file, so they will automatically be generated correctly. Once all missions have been completed by a player, the player can use the "**/nbt claim**" command to collect their rewards, which can be items, money, TeamPoints or even command execution. It is possible to force progress with "**/nbt Progress <PLAYER> <MISSION> {AMOUNT}**". To calculate player progress you need to run the command "**/nbt Admin ProcessQuest**", this is not in real time to avoid lags, to make it almost real time you can set (as in the default configuration) this command when displaying the QuestMenu UI. To retrieve their rewards, the player can at any time use the "**/nbt Claim**" command. If the missions are not to your liking you can force them to be deleted with "**/nbt Admin PurgeQuest**". You can force the initialization check with "**/nbt Admin InitQuest**".

  To claim a reward of each type, the player need to have the permission of the followed type. So:
  - nbteams.quests.Daily
  - nbteams.quests.Donor
  - nbteams.quests.Weekly
  - nbteams.quests.Monthly
  
### Economy system
You have access to the command ```/nbecon <Add|Balance|Convert|Currency|Interest|Pay|Remove|Set> {Player} {Amount} {Currency}```.
  
### Command interpreter
The command interpreter breaks down the command sent, if it starts with a "/" it will simulate the execution of the command by the player in question, if it detects a "!" it will send the command via the server. The alias {PLAYER} is available and is replaced by the player's name.

### NPC interaction
In the general configuration file you have a category "NPC_Commands", you can add the name of an NPC **(Pixelmon is required)**, e.g. when the player right-clicks on an NPC named "QUEST_NPC", the quest menu will be displayed for the player.

### Are you developper ?
Several APIs are available, contact me for more information, a dedicated section will be created in the wiki. 

# Licensed server
*Have you found a server that uses NBTeams without permission? Contact me quickly.*<br><br>
**Forge version**: PixelmonInfinity, PokeHills, PokeClash<br>
**Sponge version**: Frontier Pixelmon, Miner.GG, PixelmonCraft<br>
**Deprecated version**: Livadia<br>
