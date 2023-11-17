# Faster Fps: Quake II Remastered mod for faster gameplay in solo

## Summary

Easily rush levels, instant weapon switch, grapple, efficient auto-save.

## Gameplay overview

With this mod you can play fast in the existing campaigns, you rush through the levels, almost like a speedrunner, but you don't need to know the levels and you can kill everyone.  
Your weapons are more powerful, and you takes less damage, you easily kill loads of monsters.  

Use only Super Shootgun, Machine Gun, Rocket Launcher and Rail Gun.  
You get them directly on a new game, and all ammo items are still useful because they give you a small amount of ammo for those main weapons.

Weapon switch is now really instantaneous, enjoy chaining kills with really distinct weapons.  

Fly with a fast grapple, and rocket jump without taking self damage.  

Almost never create a savegame, the mod has an auto-save every 30 seconds on different slots.  

Use compass when you have any doubt, you're here to run and shoot fast, not to block on closed doors.  
Ignore items, no need to worry about the good timing for their use.  

The mod is mainly designed for the campaign in medium difficulty mode.  
If you want some changes for your personal taste of gameplay, you can, almost all changes of this mod are easily customizable with configuration variables.  

## Installation

Unzip the contents into "%USERPROFILE%\Saved Games\Nightdive Studios\Quake II\" (%USERPROFILE% gets you something like that: "C:\Users\MY_USER_NAME\").  
You should have a "fasterfps" folder in there, alongside the existing "baseq2", with "game_x64.dll" inside.  

Launch the game with the command line parameter added:  
```
+set game fasterfps
```
In Steam, Gog and Epic you can customize the launch options in the properties of the game.  

Or you can create on new manual shortcut on the game, example:  
```
C:\MyGames\QuakeII\ptah_Shipping_Playfab_EGS_x64.exe +set game fasterfps
```

While at it, you can also add the "-skipmovies" command line for a faster start of the game.  

Less convenient alternative to the command line: start the game, open the console, enter "game fasterfps".  

## Key binding

The mod archive includes suggested keybinds with the keybinds.cfg and autoexec.cfg files.  
The default is qwerty with jump on right click and grapple on space bar.  
You can override them with the files in the "keybinds variants" directory, there are variants for azerty and jump with space bar.  

Default keys:
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
Variable: ff_fastest_weapon_switch, 0 or 1, default value is 1  
The g_instant_weapon_switch and g_quick_weapon_switch existed outside of this mod, but it's not instantaneous at all.  

- You can launch a grapple. No need to switch weapon to use it. See the "Key binding" section for the hotkey.  
If you prefer the independent item CTF grapple, you also have it.  
Variables:  
  - g_grapple_fly_speed, default value is changed to 3000 (it was 650), the variable is already in the game without this mod, the max value is 10000 (because sv_maxvelocity is updated to this value)
  - g_grapple_pull_speed, default value is 650, the variable is already in the game without this mod
  - ff_grapple_sky, default value is 0, set it to 1 if you want to grapple the sky
  - ff_grapple_initdamage, default value is 1, damage done on initial hooking
  - ff_grapple_damage, default value is 1, integer, not sure what it does ¯|_(ツ)_/¯
  - ff_grapple_maxdamage, default value is 1
  - ff_grapple_delay, default value is 0.0, time in seconds between 2 grapple
  - ff_grapple_blue, default value is 0, set it to 1 to have a blue grapple instead of the red one
  - ff_grapple_diameter, default value is 4
  - ff_grapple_sound_volume_main, default value is 0.3
  - ff_grapple_sound_volume_secondary, default value is 0.7  

- The mod has an auto-save every 30 seconds on different slots. Every game should have this feature.  
Variables:  
  - ff_autosave_enabled, 0 or 1, default value is 1  
  - ff_autosave_interval_in_seconds, default value is 30  
  - ff_autosave_slot_count, default value is 10  

- The player does more damage, and receive less damage, because I think it's more fun to shoot many monsters than one big, while rushing through levels.  
The value depends of the campaign difficulty choice, but you can override the variables.  
You always have the maximum number of monsters, it doesn't depend of the campaign difficulty anymore.  
The mod is mainly designed to play in medium difficulty.  
Variables:  
  - easy
    - ff_player_damage_sent_multiplier is 3
    - ff_player_damage_received_multiplier is 0.5
  - medium
    - ff_player_damage_sent_multiplier is 3
    - ff_player_damage_received_multiplier is 0.7
  - hard
    - ff_player_damage_sent_multiplier is 2
    - ff_player_damage_received_multiplier is 0.7
  - nightmare
    - ff_player_damage_sent_multiplier is 1.5
    - ff_player_damage_received_multiplier is 1

- When you start a new game you already have the main weapons: Super Shootgun, Machine Gun, Rocket Launcher and Rail Gun, because I think that other weapons are similar or less interesting.  
But if you prefer differently, you still have other weapons, with ammo and more damage.  
Variables:  
  - ff_give_main_weapons_at_start, 0 or 1, default value is 1  
  - ff_start_ammo_shootgun, default value is 40  
  - ff_start_ammo_machinegun, default value is 90  
  - ff_start_ammo_rocket, default value is 20  
  - ff_start_ammo_railgun, default value is 15  

- Any ammo item you pick gives some ammo for the main weapons.  
For example, if you pick one rocket ammo item, you'll get 2 shootgun cells, 4 machine gun bullets, 0.5 rockets, 0.4 railgun slugs.  
0.5 means that you have to pick 2 ammo items to get 1 rocket.  
If you pick an ammo item for a weapon that is not one the 4 main weapons, you also get this weapon ammo in addition of the 4 others.  
This behavior is necessary for the non-main weapons ammo items to still be useful, and to have ammo for the main weapons at the first levels.  
Variables:  
  - They are split for each campaign. The "default" variables are used for the base campaign and for the maps that do not belong to a campaign.
  - ff_extra_ammo_default_shootgun, default value is 2.0
  - ff_extra_ammo_default_machinegun, default value is 4.0
  - ff_extra_ammo_default_rocket, default value is 0.7
  - ff_extra_ammo_default_railgun, default value is 0.4
  - ff_extra_ammo_call_of_the_machine_shootgun, default value is 2.0
  - ff_extra_ammo_call_of_the_machine_machinegun, default value is 4.0
  - ff_extra_ammo_call_of_the_machine_rocket, default value is 0.7
  - ff_extra_ammo_call_of_the_machine_railgun, default value is 0.4
  - ff_extra_ammo_the_reckoning_shootgun, default value is 3.0
  - ff_extra_ammo_the_reckoning_machinegun, default value is 6.0
  - ff_extra_ammo_the_reckoning_rocket, default value is 1.0
  - ff_extra_ammo_the_reckoning_railgun, default value is 0.7
  - ff_extra_ammo_ground_zero_shootgun, default value is 2.0
  - ff_extra_ammo_ground_zero_machinegun, default value is 4.0
  - ff_extra_ammo_ground_zero_rocket, default value is 0.7
  - ff_extra_ammo_ground_zero_railgun, default value is 0.4
  - ff_extra_ammo_quake64_shootgun, default value is 3.0
  - ff_extra_ammo_quake64_machinegun, default value is 6.0
  - ff_extra_ammo_quake64_rocket, default value is 1.0
  - ff_extra_ammo_quake64_railgun, default value is 0.7

- The player doesn't receive damage from its own weapon, so you can abuse rocket jumps.  
Rocket jump power is configurable by a variable, but it is not changed from the vanilla game.  
Variables:  
  - ff_self_damage, 0 or 1, default value is 0  
  - ff_rocket_jump_power, default value is 1600  

- The player doesn't receive damage from falling, because it can often occurs with the grapple.  
Variable: ff_fall_damage_multiplier, default value is 0.0

- The rocket area damage radius is 1.5x larger, for rockets launched by the player.  
Variable: ff_player_rocket_radius_scale, default value is 1.5  

- The bullets from the machine gun have no spread, because I like when my weapon shoots where I aim.  

- You have more air control. To turn a corner, you have to release the forward key and strafe.  
Variable: sv_airaccelerate, default value is 10, original game value was 0

- A speedometer can be displayed.  
Variable: ff_speedometer, default value is 0, set it to 1 to display it

- You can adjust the volume of the jump sound effect.  
Variable: ff_jump_sound_volume, between 0 and 1, default value is 0.7, set it to 1 to revert it to the value of the original game

- Barrels always explode immediately, like in original Quake 2. Imported from the Unmaster mod.  
Variable: ff_barrel_delay, 0 or 1, default value is 0  

- When you click on the weapon hotkey of the already selected weapon, it doesn't cycle to another weapon, because it's unnecessary and annoying in this mod.  
Variable: ff_weapon_chains, 0 or 1, default value is 0  

- The following changes are done because I prefer to quickly kill many dumb monsters.  

- Monsters will not duck projectiles, like in original Quake 2. Imported from the Unmaster mod.  
Variable: ff_monster_duck, 0 or 1, default value is 0  

- Monsters will not strafe to avoid grenades, like in original Quake 2. Imported from the Unmaster mod.  
Variable: ff_monster_sidestep, 0 or 1, default value is 0  

- Monsters stop shooting when losing sight. Imported from the Unmaster mod.  
Variable: ff_monster_blindfire, 0 or 1, default value is 0  

- Monsters can't see you when you're behind them and tell each other that you're there. Imported from the Unmaster mod.  
Variable: ff_monster_hyperaware, 0 or 1, default value is 0  

- Monsters stay on the platforms/floors they spawn on, like in original Quake 2. Imported from the Unmaster mod.  
Variable: ff_monster_walkjump, 0 or 1, default value is 0  

## Other information

Source code: https://github.com/yrelof/quake2-rerelease-dll-fasterfps  

Mod coded for the "Update 1" version of Quake 2 Remastered (from 2023-10-03).  

The mod also works with the additional campaigns and with the Coop.

Save games should be compatible anyway if you copy them to the mod folder (baseq2\save to fasterfps\save), but you will not get automatically the main weapons.  

To customize mod variables, edit the "settings.cfg" file in the mod directory and add this kind of line:  
```
set ff_player_damage_sent_multiplier "2"
```
You can also run the command in the game console, but the change will be lost when closing the game.  

Some changes come from the Unmaster mod, they are specified in the "Features" section. Link: https://github.com/nickgovier/Q2unmaster  

The off-hand grapple comes from the Lithium mod: http://quake2.lithium.com  
The code used comes from the Lithium remaster port: https://github.com/KyperTrast/lithium-minus

The "FasterFps" mod name means "Faster First Person Shooter", a reference to the "Fast FPS" term.  

## Changelog

v2.0.0:
- add off-hand grapple from the Lithium mod
- campaign difficulty choice handling
  - always the maximum of monster
  - difficulty choice impacts player_damage_sent_multiplier and player_damage_received_multiplier but it still can be overridden by user
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