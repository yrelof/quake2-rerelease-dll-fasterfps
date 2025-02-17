# Faster Quake 2: mod for faster gameplay in solo on Quake II Remastered

## Summary

Easily rush levels, instant weapon switch, grapple, efficient auto-save.

Demo video: https://www.youtube.com/watch?v=ighEUIIcmt4

## Gameplay overview

With this mod you can play fast in the existing campaigns, you rush through the levels, almost like a speedrunner, but you don't need to know the levels and you can kill everyone.  

Fly with a fast grapple, rocket jump without taking self damage and take turns at high speed with more air control.  

Weapon switch is now really instantaneous.  
There are a lot of monsters but your weapons are more powerful and you takes less damage, so you smoothly kill loads of monsters.  

Use only really distinct weapons: Super Shootgun, Machine Gun, Rocket Launcher and Rail Gun.
You get them directly on a new game, and all ammo items are still useful because they give you a small amount of ammo for those main weapons.

Almost never create a savegame, the mod has an auto-save every 30 seconds on different slots.  

Use compass when you have any doubt, you're here to run and shoot fast, not to block on closed doors.  
Ignore items, no need to worry about the good timing for their use.  

The mod is mainly designed for the campaign in medium difficulty mode.  
It also works in coop.  
If you want some changes for your personal taste of gameplay, you can, almost all changes of this mod are easily customizable with configuration variables.  

## Installation

Unzip the contents into:
```
C:\Users\[MY_USER_NAME]\Saved Games\Nightdive Studios\Quake II\
```
Replace [MY_USER_NAME] by your Windows user name (or you can paste %USERPROFILE% in the file explorer address bar to go to your user directory).
You should now have a "fasterquake2" folder in there, alongside the existing "baseq2", with multiple files inside.  
Warning: it's wrong if you have a "FasterQuake2Mod" folder and/or a unique folder inside the folder.
- Good path:  Nightdive Studios\Quake II\fasterquake2\game_x64.dll
- Wrong path: Nightdive Studios\Quake II\FasterQuake2Mod\fasterquake2\game_x64.dll
- Wrong path: Nightdive Studios\Quake II\fasterquake2\fasterquake2\game_x64.dll

In your game launcher (Steam, Epic, Gog...), open the properties of the game and customize the launch options to add:
```
+set game fasterquake2
```
Detailed steps for each launcher:
- In steam: right click on the game, "Properties", stay on the "General" tab, scroll down to the bottom, "launch options", add the text.
- In Epic: right click on the game, "Manage", scroll down to the bottom, check "Launch options", add the text.
- In Gog: right click  on the game, "Manage installation", "Configure...", "features" tab, check "Launch parameters / Custom executables / arguments", click "Duplicate" of the Quake 2 Remastered, scroll down to the bottom, add text in "Arguments", check "Default executable".

While at it, you can also add the "-skipmovies" option for a faster launch of the game.  

Less convenient alternative than the launch option: start the game, open the console, enter "game fasterquake2".  

Read the "Key binding" doc section under, especially for azerty keyboard players.

If you are updating from v1 or v2 of the mod (before the renaming):
  - if you want to keep your savegames: the mod folder was named "fasterfps", keep it like that, add and override the content of the new "fasterquake2" folder to it. Keep the old launch option ("+set game fasterfps"). It's better to do like that because the savegame files seems to have an hard-coded path inside, so the new saves after loading will be created in the "fasterfps" folder anyway.
  - if you customized configuration variables in "settings.cfg": the variable prefix has changed form "ff_" to "fq_", update them in "settings.cfg" (in the new "fasterquake2" folder if you have it). See also the doc about campaign difficulty choice.
  - you can read the changelog at the bottom of this file.

## Key binding

The mod archive includes suggested keybinds with the keybinds.cfg and autoexec.cfg files.  
The default is qwerty with jump on right click and grapple on space bar.  
You can override them with the files in the "keybinds variants" directory, there are variants for azerty and jump with space bar.  

Suggested keys:
- WASD/ZQSD: up, left, down, right
- left mouse: attack
- right mouse: jump
- space: grapple
- tabulation: compass
- E: super shootgun  
- A/Q: machine gun  
- F: rocket launcher  
- C: rail gun (to press with the thumb)  
- R: items wheel (usually unused)
- T: weapons wheel (usually unused)
- shift: crouch

You can't rebind the grapple key from the menu, you have to edit the autoexec.cfg file manually.

## Features

- When you switch weapons, it's really instantaneous, because it's frustrating to have to wait for the shoot cooldown before switching, now you can chain rocket and rail shoot for example.  
Variable: fq_fastest_weapon_switch, 0 or 1, default value is 1  
The g_instant_weapon_switch and g_quick_weapon_switch existed outside of this mod, but it's not instantaneous at all.  

- You can launch a grapple. No need to switch weapon to use it. See the "Key binding" section for the hotkey.  
If you prefer the independent item CTF grapple, you also have it.  
Variables:  
  - g_grapple_fly_speed, default value is changed to 3000 (it was 650), the variable is already in the game without this mod, the max value is 10000 (because sv_maxvelocity is updated to this value)
  - g_grapple_pull_speed, default value is 650, the variable is already in the game without this mod
  - fq_grapple_sky, default value is 0, set it to 1 if you want to grapple the sky
  - fq_grapple_initdamage, default value is 1, damage done on initial hooking
  - fq_grapple_damage, default value is 1, integer, not sure what it does ¯|_(ツ)_/¯
  - fq_grapple_maxdamage, default value is 1
  - fq_grapple_delay, default value is 0.0, time in seconds between 2 grapple
  - fq_grapple_blue, default value is 0, set it to 1 to have a blue grapple instead of the red one
  - fq_grapple_diameter, default value is 4
  - fq_grapple_sound_volume_main, default value is 0.3
  - fq_grapple_sound_volume_secondary, default value is 0.7  

- You have more air control. To turn a corner, you have to strafe and release the forward key.  
Variable: sv_airaccelerate, default value is 10, original game value was 0

- The mod has an auto-save every 30 seconds on different slots. Every game should have this feature.  
Variables:  
  - fq_autosave_enabled, 0 or 1, default value is 1  
  - fq_autosave_interval_in_seconds, default value is 30  
  - fq_autosave_slot_count, default value is 10  

- You always have the maximum number of monsters, it doesn't depend of the campaign difficulty anymore.  
Variable: fq_max_monsters_in_any_difficulty, 0 or 1, default value is 1  

- The player does more damage, and receive less damage, because I think it's more fun to shoot many monsters than one big, while rushing through levels.  
The value depends of the campaign difficulty choice, but you can override the variables.  
The mod is mainly designed to play in medium difficulty.  
Variables:  
  - easy
    - fq_player_damage_sent_multiplier is 3
    - fq_player_damage_received_multiplier is 0.5
  - medium
    - fq_player_damage_sent_multiplier is 3
    - fq_player_damage_received_multiplier is 0.7
  - hard
    - fq_player_damage_sent_multiplier is 2
    - fq_player_damage_received_multiplier is 0.7
  - nightmare
    - fq_player_damage_sent_multiplier is 1.5
    - fq_player_damage_received_multiplier is 1

- When you start a new game you already have the main weapons: Super Shootgun, Machine Gun, Rocket Launcher and Rail Gun, because I think that other weapons are similar or less interesting.  
But if you prefer differently, you still have other weapons, with ammo and more damage.  
Variables:  
  - fq_give_main_weapons_at_start, 0 or 1, default value is 1  
  - fq_start_ammo_shootgun, default value is 40  
  - fq_start_ammo_machinegun, default value is 90  
  - fq_start_ammo_rocket, default value is 20  
  - fq_start_ammo_railgun, default value is 15  

- Any ammo item you pick gives some ammo for the main weapons.  
For example, if you pick one rocket ammo item, you'll get 2 shootgun cells, 4 machine gun bullets, 0.7 rockets, 0.4 railgun slugs.  
A value of 0.5 means that you have to pick 2 ammo items to get 1 ammo.  
If you pick an ammo item for a weapon that is not one of the 4 main weapons, you also get this weapon ammo in addition of the 4 others.  
This behavior is necessary for the non-main weapons ammo items to still be useful, and to have ammo for the main weapons at the first levels.  
Variables:  
  - fq_extra_ammo_enabled, 0 or 1, default value is 1
  - The following variables are split for each campaign. The "default" variables are used for the base campaign and for the maps that do not belong to a campaign.
  - fq_extra_ammo_default_shootgun, default value is 2.0
  - fq_extra_ammo_default_machinegun, default value is 4.0
  - fq_extra_ammo_default_rocket, default value is 0.7
  - fq_extra_ammo_default_railgun, default value is 0.4
  - fq_extra_ammo_call_of_the_machine_shootgun, default value is 2.0
  - fq_extra_ammo_call_of_the_machine_machinegun, default value is 4.0
  - fq_extra_ammo_call_of_the_machine_rocket, default value is 0.7
  - fq_extra_ammo_call_of_the_machine_railgun, default value is 0.4
  - fq_extra_ammo_the_reckoning_shootgun, default value is 3.0
  - fq_extra_ammo_the_reckoning_machinegun, default value is 6.0
  - fq_extra_ammo_the_reckoning_rocket, default value is 1.0
  - fq_extra_ammo_the_reckoning_railgun, default value is 0.7
  - fq_extra_ammo_ground_zero_shootgun, default value is 2.0
  - fq_extra_ammo_ground_zero_machinegun, default value is 4.0
  - fq_extra_ammo_ground_zero_rocket, default value is 0.7
  - fq_extra_ammo_ground_zero_railgun, default value is 0.4
  - fq_extra_ammo_quake64_shootgun, default value is 3.0
  - fq_extra_ammo_quake64_machinegun, default value is 6.0
  - fq_extra_ammo_quake64_rocket, default value is 1.0
  - fq_extra_ammo_quake64_railgun, default value is 0.7

- The player doesn't receive damage from its own weapon, so you can abuse rocket jumps.  
Rocket jump power is configurable by a variable, but it is not changed from the vanilla game.  
Variables:  
  - fq_self_damage, 0 or 1, default value is 0  
  - fq_rocket_jump_power, default value is 1600  

- The player doesn't receive damage from falling, because it can often occurs with the grapple.  
Variable: fq_fall_damage_multiplier, default value is 0.0

- The rocket area damage radius is 1.5x larger, for rockets launched by the player.  
Variable: fq_player_rocket_radius_scale, default value is 1.5  

- The bullets from the machine gun have no spread, because I like when my weapon shoots where I aim.  

- A speedometer can be displayed.  
Variable: fq_speedometer, default value is 0, set it to 1 to display it

- You can adjust the volume of the jump sound effect.  
Variable: fq_jump_sound_volume, between 0 and 1, default value is 0.7, set it to 1 to revert it to the value of the original game

- Barrels always explode immediately, like in original Quake 2. Imported from the Unmaster mod.  
Variable: fq_barrel_delay, 0 or 1, default value is 0  

- When you click on the weapon hotkey of the already selected weapon, it doesn't cycle to another weapon, because it's unnecessary and annoying in this mod.  
Variable: fq_weapon_chains, 0 or 1, default value is 0  

- Doors open faster and at longer range, to avoid blocking when you move at high speed  
Variables:
  - fq_door_trigger_expand, default value is 300, it was 60 without the mod
  - fq_door_trigger_expand_in_height, 0 or 1, default value is 0, so you also open doors from above and under
  - fq_door_opening_speed, default value is 500, it was 100 without the mod

- The following changes are done because I prefer to quickly kill many dumb monsters.  

- Monsters will not duck projectiles, like in original Quake 2. Imported from the Unmaster mod.  
Variable: fq_monster_duck, 0 or 1, default value is 0  

- Monsters will not strafe to avoid grenades, like in original Quake 2. Imported from the Unmaster mod.  
Variable: fq_monster_sidestep, 0 or 1, default value is 0  

- Monsters stop shooting when losing sight. Imported from the Unmaster mod.  
Variable: fq_monster_blindfire, 0 or 1, default value is 0  

- Monsters can't see you when you're behind them and tell each other that you're there. Imported from the Unmaster mod.  
Variable: fq_monster_hyperaware, 0 or 1, default value is 0  

- Monsters stay on the platforms/floors they spawn on, like in original Quake 2. Imported from the Unmaster mod.  
Variable: fq_monster_walkjump, 0 or 1, default value is 0  

## Save games import

If you want to continue your progression from the base game into the modded game, you have 3 solutions:

- First solution, choose the level from the menu:
  - in the main menu: select "solo" then "level choice"
  - you'll have the weapons and ammos that are configured by default for the level

- Second solution, start a new game and jump to the level using the console:
  - start Quake2 without the mod, load your save, open the console (the key under the escape key), type "mapname" to get the name of the current map
  - start Quake2 with the mod, start a new game, open the console, type "map [YOUR_MAP_NAME]" (replace [YOUR_MAP_NAME] by the retrieved map name)
  - this solution is more precise than the first solution (there are more maps than in the menu), but you'll start without weapon and item, so you have to use the console to get them: "give railgun" for example. You can see the list on https://www.quakewiki.net/console/console-commands/quake-2-console-commands

Save games are compatible if you copy them to the mod folder (baseq2\save to fasterquake2\save), but it seems that the savegame files have an hard-coded path inside, so the new saves after loading are created in the old directory anyway, so they are not displayed when you want to load.

- Last solution allows you to use exactly your savegame. You create a directory link so the two save directories are in reality only one directory (replace [MY_USER_NAME] by your windows user name in the commands):
  - make a full backup of your "C:\Users\[MY_USER_NAME]\Saved Games\Nightdive Studios\Quake II" directory
  - delete the "C:\Users\[MY_USER_NAME]\Saved Games\Nightdive Studios\Quake II\fasterquake2\save" directory
  - open a PowerShell console in Windows to type:
  ```
  New-Item -Path "C:\Users\[MY_USER_NAME]\Saved Games\Nightdive Studios\Quake II\fasterquake2\save" -ItemType SymbolicLink -Value "C:\Users\[MY_USER_NAME]\Saved Games\Nightdive Studios\Quake II\baseq2\save"
  ```
  (if you use the old cmd console it's:
  ``` 
  mklink /D "C:\Users\[MY_USER_NAME]\Saved Games\Nightdive Studios\Quake II\fasterquake2\save" "C:\Users\[MY_USER_NAME]\Saved Games\Nightdive Studios\Quake II\baseq2\save"
  ```
  )  
  Now when the game will access the "fasterquake2\save" directory it will use "baseq2\save" in reality.  

  To revert the changes, you just have to delete "C:\Users\[MY_USER_NAME]\Saved Games\Nightdive Studios\Quake II\fasterquake2\save" (that is a link, not a real directory).

## Other information

Source code: https://github.com/yrelof/quake2-rerelease-dll-FasterQuake2

Mod coded for the "Update 1" version of Quake 2 Remastered (from 2023-10-03).  

The mod also works with the additional campaigns and with the Coop.

To customize mod variables, edit the "settings.cfg" file in the mod directory and add this kind of line:  
```
set fq_speedometer "1"
```
You can also run the command in the game console, but the change will be lost when closing the game.  
If your "settings.cfg" file is reset every time you start the game, then set the file as read-only.

If you ever get stuck in a level, with the GPS pointing in a wrong direction (it can occurs when rushing with the grapple), you can restart the level (it's at the top in the load game menu) and then follow the GPS more closely to avoid glitching the level.

Some changes come from the Unmaster mod, they are specified in the "Features" section. Link: https://github.com/nickgovier/Q2unmaster

The off-hand grapple comes from the Lithium mod: http://quake2.lithium.com  
The code used comes from the Lithium remaster port: https://github.com/KyperTrast/lithium-minus

## Changelog

v3.1.0:
- doors open faster and at longer range
- fix build because it seems that a VS2022 update broke format usage

v3.0.1:
- fix fq_monster_walkjump configuration variable

v3.0.0:
- rename mod from "Faster Fps" to "Faster Quake 2"
  - the mod in now installed in a "fasterquake2" folder
  - the configuration variables prefix has changed form "ff_" to "fq_"
  - see the "Installation" doc section for instructions if you update from a previous version
- fix keybinds variants

v2.1.0:
- fix crash in coop (the joining player crashed)
- add missing configuration variables for max monsters in any difficulty and extra ammo enabled
- autosave interval variable change in console is now instantly applied

v2.0.0:
- add off-hand grapple from the Lithium mod
- campaign difficulty choice handling
  - always the maximum of monster
  - difficulty choice impacts player_damage_sent_multiplier and player_damage_received_multiplier but it still can be overridden by user
  - the mod is now designed for the medium difficulty mode
- different extra ammo handled for each campaign
- tweak ammo quantity
- increase sv_airaccelerate to have air control
- add speedometer (ff_speedometer variable)
- add cfg files for keybinds variants
- add ff_fall_damage_multiplier cfg variable, default to 0.0
- add ff_jump_sound_volume cfg variable, default to 0.7
- increase g_grapple_fly_speed to 3000 (and sv_maxvelocity to 10000)
- add config variables for grapple

v1.1.0:
- first public release