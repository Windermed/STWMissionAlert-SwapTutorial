
# HOW TO DO MISSION ALERT SWAPS FOR STW 2023 ( written by @Windermed_ ) 

This entire tutorial was the result of hours of research and trial and error after how annoyed i was at the amount of gatekeeping involved from those who knew about it and because of that, I decided to figure out how to do it on my own and release it to the public out of spite of those who are gatekeeping/selling it and so people don't waste their money on methods that will probably be patched soon.

credit isn't needed, but would be really appreciated if you decide to share/repost this or make a video tutorial on this! anyways, 

here is the method, hope you all enjoy!

**DISCLAIMER: JUST LIKE WITH ANY OTHER FORTNITE EXPLOIT/GLITCH, THIS MAY OR MAY NOT HAVE A BAN RISK. I HIGHLY RECOMMEND TO DO THIS ON AN ALT ACCOUNT IF POSSIBLE. 
 YOU ASSUME ALL RISK AND RESPONSIBILITY BY DOING THIS AND I AM NOT RESPONSIBLE FOR ANY POTENTIAL BANS THAT MAY OR MAY NOT OCCUR USING THIS METHOD.**


What you will need:
basic computer knowledge
Latest fortnite client (obviously)
Fiddler Classic
Any server backend capable of XMPP
latest dump of stw’s mission data (the data containing all of the missions such as positions, rewards, etc)
an SSL bypass that works on latest
A DLL Injection program (I used Xenos Injector but any work!)
**NOTE: ALL LINKS WILL BE PROVIDED AT THE BOTTOM OF THIS TEXT.** 


## **TUTORIAL:**

Step 1: Download Fiddler Classic and once you do, make sure ROOT CERTIFICATE is installed as well as check the first 2 checkboxes in the options (important)

Step 2: ensure you have a backend is capable of doing what i said above however if you do not have one, feel free to use a backend such as LawinServerV1 as it will work with this tutorial. (Credit to Lawin!)

Step 3: compile an SSL bypass that works on latest. If you do not have one, feel free to download and compile Cobalt as that works on latest. (Credit to Milxnor!) 

Step 4: if using Cobalt, follow the instructions on it's github page to compile it for hybrid servers and ensure that you replace the appropiate launchers as well then come back here.

Step 5: you'll need to find a way to dump the mission data for STW as you'll need the latest dump everytime you want to do this (or every reset basically).
The place where you'll need to find the data is for "/fortnite/api/game/v2/world/info". I can't go into too much detail on how to do so as it'll clog up the tutorial 
but if you need to find ways there are multiple methods on accessing the API to dump the mission data (manually authenticating via the Epic API, using a bot/program that does it, etc.) 
there are plenty of tools out there you can use to dump it so feel free to look for them. You can also try to find another fortnite api that may allow you access it without needing to authenticate.

Step 6: once that's done, get the data in raw text and ensure it is in json format. the name for the file isn't relevant but for this tutorial, let's call it "stw.json"

Step 7: once done, ensure you have an idea on what missions whos alert you'd like to swap (for example, say a PL 140 mission has a legendary survivor and you want that reward on a PL 76 mission.)
Note: if you are trying to swap XP, keep a note of the quantity of XP it gives. it'll be easier to search for it in the json)

Step 8: go inside your json file and find the appropiate "missionAlertRewards" attribute that has the rewards of the mission you want/are swapping from. 
also depending on the mission, you may need to do one of the following to fully swap it (i recommend doing all of the steps, but you may be able to get away with only doing one)

	1. swap the tileIndex number from the alerts rewards that you have EXAMPLE: a 140 mission alert's tileIndex may be 180, but a PL 72 alert mission tileIndex may be 202. change the 140's tileIndex to 202 and change the PL 72's to 180)
   
	2. copy the entire thing from it's starting attribute (name i think?) all the way down to it's modifier. (or the comma bracket that closes it off)

Step 9: once you've swapped out the values from both missions. (or whatever mission you have) then the next step will be to Open fiddler and go to the AutoResponder tab
ensure you've checked "Enable Rules" and "Unmatched requests passthrough". once done, click "Add Rule" and on the StringToMatch box paste this endpoint:
"https://fngw-mcp-gc-livefn.ol.epicgames.com/fortnite/api/game/v2/world/info" (without the quotes) 

Step 10: on the second box, you'll have the option to import a file. click on the drop arrow and go all the way down until you see "Find a file".
from there, locate your modified stw mission json and import it.

This will ensure that when the endpoint for missions gets loaded, it'll respond with your modified JSON file instead of the one from epic's servers.

Step 11: once that's done, you've finally did it! now the next step is to run your server

***WARNING: ENSURE YOU HAVE REPLACED THE OTHER EXE FILES (BE, EAC, EAC_EOS) WITH COPIES OF "FortniteClient-Win64-Shipping" BEFORE PROCEEDING FURTHER
IGNORING THIS STEP WILL TRIGGER THE ANTI-CHEAT AND MAY RESULT IN A BAN.***


Step 12: before launching, quickly go to your DLL injection program of choice and select the Cobalt DLL you have compiled (or whatever SSL bypass you use)


Step 13: go to your binaries and launch "FortniteClient-Win64-Shipping.exe". once you are loading in quickly inject the DLL to "FortniteClient-Win64-Shipping_EAC_EOS" (or whatever process shows up, just don't inject it to FortniteLauncher!)

Step 14: If you've done everything correctly, you should begin to see console logs from another tab that shows that fortnite is loading.

Step 15: Quickly go to STW (wether through game select, or the playlist in BR) and once done, go to your missions and find the mission you modified with another mission's alert rewards.

Step 16: If everything is done correctly, you should see that the rewards were successfully swapped which means it worked on your end.

Step 17: Enjoy!

**NOTE**: The steps for the backend may or may not be needed. I simply decided to include it here as it allows you to utilize an SSL bypass which will make this process more safer and effective.
also you may not be able to load into a match. that is intentional since you are using your own backend which won't work with loading in-game. In order to go into a mission via this method you'll need to invite someone (or yourself) to your party
either while looking through a mission, or when you load into the lobby of a mission.

also i had some success using this method to load into a mission in-game and obtain the rewards (using an alt) but results may vary. 
if the mission does not load with the rewards you swapped or it crashes or whatever You will need to find another mission to swap with unfortunately.

Hopefully this might garner some interest in STW and also put an end to those who are trying to rip people off by selling the method on how to do alert swaps. I've also included a list of file names of STW resources below which may help if you need to know what the file name of a certain item your swapping with is called, hope it helps!

whew this took me a while to write, but i hope it was clear enough to those reading it!

 there may  be some grammar mistakes or steps that i didn't clarify enough on and if they're are (or you have a question) then feel free to contact me on Discord (@Windermed) I'll try to respond to everyone as quick as i can, but for now i'm just gonna rest since i've spent the past 10-12 hours researching this method lol



**LINKS THAT MAY BE HELPFUL**: (Credit to everyone linked below!)
https://github.com/Lawin0129/LawinServer 

https://github.com/Milxnor/Cobalt

https://github.com/DarthTon/Xenos

https://github.com/LeleDerGrasshalmi/FortniteEndpointsDocumentation/blob/main/Fortnite/SaveTheWorld/Missions.md (For STW mission data)

- 

Have a hee-great day, ho!

-- Windermed


**IF YOU NEED A GUIDE ON WHAT YOU NEED TO SWAP WITH/SWAP FROM, FEEL FREE TO USE THIS:
ACCOUNT RESOURCE GUIDE:**


	CURRENCY:
	campaign_event_currency - Currency of the season (might be tickets??)

	currency_xrayllama - X-Ray Llama token

	eventcurrency_adventure - Pirate Tickets

	eventcurrency_blockbuster - Blockbuster Tickets

	eventcurrency_candy - Fortnitemares Candy 

	eventcurrency_founders - Founder's Coins

	eventcurrency_lunar - Lunar Tickets

	eventcurrency_roadtrip - Road Trip Tickets

	eventcurrency_scaling - Gold 

	eventcurrency_snowballs - Snowflake Tickets

	eventcurrency_spring - Spring Tickets

	specialcurrency_daily  - Daily Coins
	
	eventcurrency_summer - Summer Tickets
	
	ALL TYPES OF XP:

		heroxp - Hero XP
		
		personnelxp - Survivor XP

		phoenixxp - Venture XP
		
		schematicxp  - Schematic XP
	
		phoenixxp_reward - Venture XP (use this if XP has a set quantity to it)
	
	PERK RELATED RESOURCES:
	

		reagent_alteration_ele_fire - FIRE-UP!

		reagent_alteration_ele_nature - AMP-UP!

		reagent_alteration_ele_water - FROST-UP!

		reagent_alteration_gameplay_generic - Core RE-PERK!

		reagent_alteration_generic  - RE-PERK!

		reagent_alteration_upgrade_r  - Rare PERK-UP!

		reagent_alteration_upgrade_sr  - Legendary PERK-UP!

		reagent_alteration_upgrade_uc  - Uncommon PERK-UP!

		reagent_alteration_upgrade_vr  - Epic PERK-UP!
		
	EVOLUTION MATERIALS:
	
		reagent_c_t01  - Pure Drop of Rain

		reagent_c_t02  - Lightning in a Bottle

		reagent_c_t03  - Eye of the Storm

		reagent_c_t04  - Storm Shard

		reagent_evolverarity_r  - Rare Flux

		reagent_evolverarity_sr  - Legendary Flux

		reagent_evolverarity_vr  - Epic Flux

		reagent_people  - Training Manual

		reagent_promotion_heroes  - Hero Supercharger

		reagent_promotion_survivors  - Survivor Supercharger

		reagent_promotion_traps  - Trap Supercharger

		reagent_promotion_weapons  - Weapon Supercharger
	
		reagent_traps  - Trap Designs

		reagent_weapons  - Weapon Designs
		
		peopleresource - People currency (no longer used)



	LLAMA/VOUCHER TOKENS:
	
		voucher_herobuyback  - Hero Recruitment Voucher

		voucher_item_buyback  - Weapon Research Voucher

		voucher_basicpack  - Mini Reward Llama

		voucher_cardpack_2021anniversary  - 2021 Birthday Llama Token

		voucher_cardpack_bronze  - Upgrade Llama Token

		voucher_cardpack_jackpot  - Legendary Troll Stash Llama Token

		voucher_custom_firecracker_r  - Firecracker Token

		voucher_founders_constructor_bundle  - Founders Constructor Bundle Token

		voucher_founders_constructor_weapon_sr  - Founders Constructor Legendary Weapon Token

		voucher_founders_constructor_weapon_vr  - Founders Constructor Epic Weapon Token

		voucher_founders_ninja_bundle  - Founders Ninja Bundle Token

		voucher_founders_ninja_weapon_sr  - Founders Ninja Legendary Weapon Token

		voucher_founders_ninja_weapon_vr  - Founders Ninja Epic Weapon Token

		voucher_founders_outlander_bundle  - Founders Outlander Bundle Token

		voucher_founders_outlander_weapon_sr  - Founders Outlander Legendary Weapon Token

		voucher_founders_outlander_weapon_vr  - Founders Outlander Epic Weapon Token

		voucher_founders_soldier_bundle  - Founders Soldier Bundle Token

		voucher_founders_soldier_weapon_sr  - Founders Soldier Legendary Weapon Token

		voucher_founders_soldier_weapon_vr  - Founders Soldier Epic Weapon Token

		voucher_founders_starterweapons_bundle  - Founders Starter Weapons Token

		voucher_generic_defender_r  - Rare Defender Token

		voucher_generic_defender_sr  - Legendary Defender Token

		voucher_generic_defender_vr  - Epic Defender Token

		voucher_generic_hero_r  - Rare Hero Token

		voucher_generic_hero_sr  - Legendary Hero Token

		voucher_generic_hero_vr  - Epic Hero Token

		voucher_generic_manager_r  - Rare Lead Survivor Token

		voucher_generic_manager_sr  - Legendary Lead Survivor Token

		voucher_generic_manager_vr  - Epic Lead Survivor Token

		voucher_generic_melee_r  - Rare Melee Weapon Token

		voucher_generic_melee_sr  - Legendary Melee Weapon Token

		voucher_generic_melee_vr  - Epic Melee Weapon Token

		voucher_generic_ranged_r  - Rare Ranged Weapon Token

		voucher_generic_ranged_sr  - Legendary Ranged Weapon Token

		voucher_generic_ranged_vr  -Epic Ranged Weapon Token

		voucher_generic_schematic_r  - Rare Schematic Token

		voucher_generic_schematic_sr  - Legendary Schematic Token

		voucher_generic_schematic_vr  - Epic Schematic Token

		voucher_generic_trap_r  - Rare Trap Token

		voucher_generic_trap_sr  - Legendary Trap Token

		voucher_generic_trap_vr  - Epic Trap Token

		voucher_generic_weapon_r  - Rare Weapon Token

		voucher_generic_weapon_sr  - Legendary Weapon Token

		voucher_generic_weapon_vr  - Epic Weapon Token

		voucher_generic_worker_r  - Rare Survivor Token

		voucher_generic_worker_sr  - Legendary Survivor Token

		voucher_generic_worker_vr  - Epic Survivor Token

	



**HERO IDs (if you need them):**



	NOTE: T01 means 1 STAR, T02 means 2 STAR, T03 means 3 STAR, T04 means 4 STAR, T05 means 5 STAR. (basically the evolution stage)



	TEST/DEV HEROES:

		"Hero:dev_testasset_commando_female" - Special Forces Ramirez

		"Hero:dev_testasset_commanod_male" - Sergeant Jonesy

		"Hero:dev_testasset_constructor_female" - Power BASE Penny

		"Hero:dev_testasset_constructor_male" - SkydiveTest Pilot Large

		"Hero:dev_testasset_hid_m_xl" - Rescue Trooper Ramirez

		"Hero:dev_testasset_ninja_female" - Sarah Claus

		"Hero:dev_testasset_ninja_male" - Deadly Blade Scorpion

		"Hero:dev_testasset_outlander_female" - Recon Scout Eagle Eye

		"Hero:dev_testasset_outlander_male" - Enforcer Grizzly
		
		"Hero:hid_commando_prototype" - Prototype Dude


	SOLDIERS:

		"Hero:hid_001_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_002_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_003_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_004_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_005_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_006_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_007_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_008_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_009_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_010_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_011_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_012_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_013_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_014_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_015_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_016_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_017_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_018_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_019_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_020_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_021_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_022_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_023_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_024_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_025_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_026_athena_commando_m" - Rescue Trooper Ramirez
		"Hero:hid_027_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_028_athena_commando_f" - Rescue Trooper Ramirez
		"Hero:hid_029_athena_commando_f_halloween" - Marine Corpse Ramirez
		"Hero:hid_030_athena_commando_m_halloween" - Skull Trooper Jonesy
		"Hero:hid_031_athena_commando_m_retro" - Skull Trooper Jonesy
		"Hero:hid_089_athena_commando_m_retrogrey - Skull Trooper Jonesy
		"Hero:hid_commando_007_r_t01" - Support Specialist Hawk
		"Hero:hid_commando_007_r_t02" - Support Specialist Hawk
		"Hero:hid_commando_007_r_t03" - Support Specialist Hawk
		"Hero:hid_commando_007_r_t04" - Support Specialist Hawk
		"Hero:hid_commando_007_sr_t01" - Support Specialist Hawk
		"Hero:hid_commando_007_sr_t02" - Support Specialist Hawk
		"Hero:hid_commando_007_sr_t03" - Support Specialist Hawk
		"Hero:hid_commando_007_sr_t04" - Support Specialist Hawk
		"Hero:hid_commando_007_sr_t05" - Support Specialist Hawk
		"Hero:hid_commando_007_uc_t01" - Support Specialist Hawk
		"Hero:hid_commando_007_uc_t02" - Support Specialist Hawk
		"Hero:hid_commando_007_uc_t03" - Support Specialist Hawk
		"Hero:hid_commando_007_vr_t01" - Support Specialist Hawk
		"Hero:hid_commando_007_vr_t02" - Support Specialist Hawk
		"Hero:hid_commando_007_vr_t03" - Support Specialist Hawk
		"Hero:hid_commando_007_vr_t04" - Support Specialist Hawk
		"Hero:hid_commando_007_vr_t05" - Support Specialist Hawk
		"Hero:hid_commando_007hw_rs01_sr_t01" - Brainiac Jonesy
		"Hero:hid_commando_007hw_rs01_sr_t02" - Brainiac Jonesy
		"Hero:hid_commando_007hw_rs01_sr_t03" - Brainiac Jonesy
		"Hero:hid_commando_007hw_rs01_sr_t04" - Brainiac Jonesy
		"Hero:hid_commando_007hw_rs01_sr_t05" - Brainiac Jonesy
		"Hero:hid_commando_007hw_sr_t01" - Ghoul Trooper Ramirez
		"Hero:hid_commando_007hw_sr_t02" - Ghoul Trooper Ramirez
		"Hero:hid_commando_007hw_sr_t03" - Ghoul Trooper Ramirez
		"Hero:hid_commando_007hw_sr_t04" - Ghoul Trooper Ramirez
		"Hero:hid_commando_007hw_sr_t05" - Ghoul Trooper Ramirez
		"Hero:hid_commando_007hw_vr_t01" - Ghoul Trooper Ramirez
		"Hero:hid_commando_007hw_vr_t02" - Ghoul Trooper Ramirez
		"Hero:hid_commando_007hw_vr_t03" - Ghoul Trooper Ramirez
		"Hero:hid_commando_007hw_vr_t04" - Ghoul Trooper Ramirez
		"Hero:hid_commando_007hw_vr_t05" - Ghoul Trooper Ramirez
		"Hero:hid_commando_008_foundersf_sr_t01" - Special Forces Ramirez
		"Hero:hid_commando_008_foundersf_sr_t02" - Special Forces Ramirez
		"Hero:hid_commando_008_foundersf_sr_t03" - Special Forces Ramirez
		"Hero:hid_commando_008_foundersf_sr_t04" - Special Forces Ramirez
		"Hero:hid_commando_008_foundersf_sr_t05" - Special Forces Ramirez
		"Hero:hid_commando_008_foundersm_sr_t01" - Special Forces Jonesy
		"Hero:hid_commando_008_foundersm_sr_t02" - Special Forces Jonesy
		"Hero:hid_commando_008_foundersm_sr_t03" - Special Forces Jonesy
		"Hero:hid_commando_008_foundersm_sr_t04" - Special Forces Jonesy
		"Hero:hid_commando_008_foundersm_sr_t05" - Special Forces Jonesy
		"Hero:hid_commando_008_r_t01" - Special Forces Banshee
		"Hero:hid_commando_008_r_t02" - Special Forces Banshee
		"Hero:hid_commando_008_r_t03" - Special Forces Banshee
		"Hero:hid_commando_008_r_t04" - Special Forces Banshee
		"Hero:hid_commando_008_sr_t01" - Special Forces Banshee
		"Hero:hid_commando_008_sr_t02" - Special Forces Banshee
		"Hero:hid_commando_008_sr_t03" - Special Forces Banshee
		"Hero:hid_commando_008_sr_t04" - Special Forces Banshee
		"Hero:hid_commando_008_sr_t05" - Special Forces Banshee
		"Hero:hid_commando_008_vr_t01" - Special Forces Banshee
		"Hero:hid_commando_008_vr_t02" - Special Forces Banshee
		"Hero:hid_commando_008_vr_t03" - Special Forces Banshee
		"Hero:hid_commando_008_vr_t04" - Special Forces Banshee
		"Hero:hid_commando_008_vr_t05" - Special Forces Banshee
		"Hero:hid_commando_009_m_r_t01" - Centurion Hawk
		"Hero:hid_commando_009_m_r_t02" - Centurion Hawk
		"Hero:hid_commando_009_m_r_t03" - Centurion Hawk
		"Hero:hid_commando_009_m_r_t04" - Centurion Hawk
		"Hero:hid_commando_009_m_sr_t01" - Centurion Hawk
		"Hero:hid_commando_009_m_sr_t02" - Centurion Hawk
		"Hero:hid_commando_009_m_sr_t03" - Centurion Hawk
		"Hero:hid_commando_009_m_sr_t04" - Centurion Hawk
		"Hero:hid_commando_009_m_sr_t05" - Centurion Hawk
		"Hero:hid_commando_009_m_vr_t01" - Centurion Hawk
		"Hero:hid_commando_009_m_vr_t02" - Centurion Hawk
		"Hero:hid_commando_009_m_vr_t03" - Centurion Hawk
		"Hero:hid_commando_009_m_vr_t04" - Centurion Hawk
		"Hero:hid_commando_009_m_vr_t05" - Centurion Hawk
		"Hero:hid_commando_009_r_t01" - Colonel Wildcat
		"Hero:hid_commando_009_r_t02" - Colonel Wildcat
		"Hero:hid_commando_009_r_t03" - Colonel Wildcat
		"Hero:hid_commando_009_r_t04" - Colonel Wildcat
		"Hero:hid_commando_009_sr_t01" - Colonel Wildcat
		"Hero:hid_commando_009_sr_t02" - Colonel Wildcat
		"Hero:hid_commando_009_sr_t03" - Colonel Wildcat
		"Hero:hid_commando_009_sr_t04" - Colonel Wildcat
		"Hero:hid_commando_009_sr_t05" - Colonel Wildcat
		"Hero:hid_commando_009_vr_t01" - Colonel Wildcat
		"Hero:hid_commando_009_vr_t02" - Colonel Wildcat
		"Hero:hid_commando_009_vr_t03" - Colonel Wildcat
		"Hero:hid_commando_009_vr_t04" - Colonel Wildcat
		"Hero:hid_commando_009_vr_t05" - Colonel Wildcat
		"Hero:hid_commando_010_bday_sr_t01" - Birthday Brigade Ramirez
		"Hero:hid_commando_010_bday_sr_t02" - Birthday Brigade Ramirez
		"Hero:hid_commando_010_bday_sr_t03" - Birthday Brigade Ramirez
		"Hero:hid_commando_010_bday_sr_t04" - Birthday Brigade Ramirez
		"Hero:hid_commando_010_bday_sr_t05" - Birthday Brigade Ramirez
		"Hero:hid_commando_010_sr_t01" - Sergeant Jonesy
		"Hero:hid_commando_010_sr_t02" - Sergeant Jonesy
		"Hero:hid_commando_010_sr_t03" - Sergeant Jonesy
		"Hero:hid_commando_010_sr_t04" - Sergeant Jonesy
		"Hero:hid_commando_010_sr_t05" - Sergeant Jonesy
		"Hero:hid_commando_010_vr_t01" - Sergeant Jonesy
		"Hero:hid_commando_010_vr_t02" - Sergeant Jonesy
		"Hero:hid_commando_010_vr_t03" - Sergeant Jonesy
		"Hero:hid_commando_010_vr_t04" - Sergeant Jonesy
		"Hero:hid_commando_010_vr_t05" - Sergeant Jonesy
		"Hero:hid_commando_011_f_v1_roadtrip_sr_t01" - Redline Ramirez
		"Hero:hid_commando_011_f_v1_roadtrip_sr_t02" - Redline Ramirez
		"Hero:hid_commando_011_f_v1_roadtrip_sr_t03" - Redline Ramirez
		"Hero:hid_commando_011_f_v1_roadtrip_sr_t04" - Redline Ramirez
		"Hero:hid_commando_011_f_v1_roadtrip_sr_t05" - Redline Ramirez
		"Hero:hid_commando_011_m_easter_sr_t01" - Rabbit Raider Jonesy
		"Hero:hid_commando_011_m_easter_sr_t02" - Rabbit Raider Jonesy
		"Hero:hid_commando_011_m_easter_sr_t03" - Rabbit Raider Jonesy
		"Hero:hid_commando_011_m_easter_sr_t04" - Rabbit Raider Jonesy
		"Hero:hid_commando_011_m_easter_sr_t05" - Rabbit Raider Jonesy
		"Hero:hid_commando_011_m_sr_t01" - Buckshot Raptor
		"Hero:hid_commando_011_m_sr_t02" - Buckshot Raptor
		"Hero:hid_commando_011_m_sr_t03" - Buckshot Raptor
		"Hero:hid_commando_011_m_sr_t04" - Buckshot Raptor
		"Hero:hid_commando_011_m_sr_t05" - Buckshot Raptor
		"Hero:hid_commando_011_r_t01" - Shrapnel Headhunter
		"Hero:hid_commando_011_r_t02" - Shrapnel Headhunter
		"Hero:hid_commando_011_r_t03" - Shrapnel Headhunter
		"Hero:hid_commando_011_r_t04" - Shrapnel Headhunter
		"Hero:hid_commando_011_sr_t01" - Shrapnel Headhunter
		"Hero:hid_commando_011_sr_t02" - Shrapnel Headhunter
		"Hero:hid_commando_011_sr_t03" - Shrapnel Headhunter
		"Hero:hid_commando_011_sr_t04" - Shrapnel Headhunter
		"Hero:hid_commando_011_sr_t05" - Shrapnel Headhunter
		"Hero:hid_commando_011_uc_t01" - Shrapnel Headhunter
		"Hero:hid_commando_011_uc_t02" - Shrapnel Headhunter
		"Hero:hid_commando_011_uc_t03" - Shrapnel Headhunter
		"Hero:hid_commando_011_vr_t01" - Shrapnel Headhunter
		"Hero:hid_commando_011_vr_t02" - Shrapnel Headhunter
		"Hero:hid_commando_011_vr_t03" - Shrapnel Headhunter
		"Hero:hid_commando_011_vr_t04" - Shrapnel Headhunter
		"Hero:hid_commando_011_vr_t05" - Shrapnel Headhunter
		"Hero:hid_commando_013_r_t01" - Demolisher Jonesy
		"Hero:hid_commando_013_r_t02" - Demolisher Jonesy
		"Hero:hid_commando_013_r_t03" - Demolisher Jonesy
		"Hero:hid_commando_013_r_t04" - Demolisher Jonesy
		"Hero:hid_commando_013_sr_t01" - Demolisher Jonesy
		"Hero:hid_commando_013_sr_t02" - Demolisher Jonesy
		"Hero:hid_commando_013_sr_t03" - Demolisher Jonesy
		"Hero:hid_commando_013_sr_t04" - Demolisher Jonesy
		"Hero:hid_commando_013_sr_t05" - Demolisher Jonesy
		"Hero:hid_commando_013_stpatricks_f_v1_sr_t01" - Four Leaf Wildcat
		"Hero:hid_commando_013_stpatricks_f_v1_sr_t02" - Four Leaf Wildcat
		"Hero:hid_commando_013_stpatricks_f_v1_sr_t03" - Four Leaf Wildcat
		"Hero:hid_commando_013_stpatricks_f_v1_sr_t04" - Four Leaf Wildcat
		"Hero:hid_commando_013_stpatricks_f_v1_sr_t05" - Four Leaf Wildcat
		"Hero:hid_commando_013_stpatricks_f_v2_sr_t01" - Highland Warrior Wildcat
		"Hero:hid_commando_013_stpatricks_f_v2_sr_t02" - Highland Warrior Wildcat
		"Hero:hid_commando_013_stpatricks_f_v2_sr_t03" - Highland Warrior Wildcat
		"Hero:hid_commando_013_stpatricks_f_v2_sr_t04" - Highland Warrior Wildcat
		"Hero:hid_commando_013_stpatricks_f_v2_sr_t05" - Highland Warrior Wildcat
		"Hero:hid_commando_013_stpatricks_m_sr_t01" - Battle Hound Jonesy
		"Hero:hid_commando_013_stpatricks_m_sr_t02" - Battle Hound Jonesy
		"Hero:hid_commando_013_stpatricks_m_sr_t03" - Battle Hound Jonesy
		"Hero:hid_commando_013_stpatricks_m_sr_t04" - Battle Hound Jonesy
		"Hero:hid_commando_013_stpatricks_m_sr_t05" - Battle Hound Jonesy
		"Hero:hid_commando_013_vr_t01" - Demolisher Jonesy
		"Hero:hid_commando_013_vr_t02" - Demolisher Jonesy
		"Hero:hid_commando_013_vr_t03" - Demolisher Jonesy
		"Hero:hid_commando_013_vr_t04" - Demolisher Jonesy
		"Hero:hid_commando_013_vr_t05" - Demolisher Jonesy
		"Hero:hid_commando_014_m_sr_t01" - Berserker Renegade
		"Hero:hid_commando_014_m_sr_t02" - Berserker Renegade
		"Hero:hid_commando_014_m_sr_t03" - Berserker Renegade
		"Hero:hid_commando_014_m_sr_t04" - Berserker Renegade
		"Hero:hid_commando_014_m_sr_t05" - Berserker Renegade
		"Hero:hid_commando_014_sr_t01" - Onslaught Headhunter
		"Hero:hid_commando_014_sr_t02" - Onslaught Headhunter
		"Hero:hid_commando_014_sr_t03" - Onslaught Headhunter
		"Hero:hid_commando_014_sr_t04" - Onslaught Headhunter
		"Hero:hid_commando_014_sr_t05" - Onslaught Headhunter
		"Hero:hid_commando_014_vr_t01" - Onslaught Headhunter
		"Hero:hid_commando_014_vr_t02" - Onslaught Headhunter
		"Hero:hid_commando_014_vr_t03" - Onslaught Headhunter
		"Hero:hid_commando_014_vr_t04" - Onslaught Headhunter
		"Hero:hid_commando_014_vr_t05" - Onslaught Headhunter
		"Hero:hid_commando_014_wukong_sr_t01" - Wukong"
		"Hero:hid_commando_014_wukong_sr_t02" - Wukong"
		"Hero:hid_commando_014_wukong_sr_t03" - Wukong"
		"Hero:hid_commando_014_wukong_sr_t04" - Wukong"
		"Hero:hid_commando_014_wukong_sr_t05" - Wukong"
		"Hero:hid_commando_015_f_v1_blockbuster_sr_t01" - Chromium Ramirez
		"Hero:hid_commando_015_f_v1_blockbuster_sr_t02" - Chromium Ramirez
		"Hero:hid_commando_015_f_v1_blockbuster_sr_t03" - Chromium Ramirez
		"Hero:hid_commando_015_f_v1_blockbuster_sr_t04" - Chromium Ramirez
		"Hero:hid_commando_015_f_v1_blockbuster_sr_t05" - Chromium Ramirez
		"Hero:hid_commando_015_m_v1_blockbuster_sr_t01" - Diecast Jonesy
		"Hero:hid_commando_015_m_v1_blockbuster_sr_t02" - Diecast Jonesy
		"Hero:hid_commando_015_m_v1_blockbuster_sr_t03" - Diecast Jonesy
		"Hero:hid_commando_015_m_v1_blockbuster_sr_t04" - Diecast Jonesy
		"Hero:hid_commando_015_m_v1_blockbuster_sr_t05" - Diecast Jonesy
		"Hero:hid_commando_015_m_v1_sr_t01" - Bullet Storm Jonesy
		"Hero:hid_commando_015_m_v1_sr_t02" - Bullet Storm Jonesy
		"Hero:hid_commando_015_m_v1_sr_t03" - Bullet Storm Jonesy
		"Hero:hid_commando_015_m_v1_sr_t04" - Bullet Storm Jonesy
		"Hero:hid_commando_015_m_v1_sr_t05" - Bullet Storm Jonesy
		"Hero:hid_commando_015_m_v1_vr_t01" - Bullet Storm Jonesy
		"Hero:hid_commando_015_m_v1_vr_t02" - Bullet Storm Jonesy
		"Hero:hid_commando_015_m_v1_vr_t03" - Bullet Storm Jonesy
		"Hero:hid_commando_015_m_v1_vr_t04" - Bullet Storm Jonesy
		"Hero:hid_commando_015_m_v1_vr_t05" - Bullet Storm Jonesy
		"Hero:hid_commando_016_f_v1_sr_t01" - Double Agent Evelynn"
		"Hero:hid_commando_016_f_v1_sr_t02" - Double Agent Evelynn"
		"Hero:hid_commando_016_f_v1_sr_t03" - Double Agent Evelynn"
		"Hero:hid_commando_016_f_v1_sr_t04" - Double Agent Evelynn"
		"Hero:hid_commando_016_f_v1_sr_t05" - Double Agent Evelynn"
		"Hero:hid_commando_016_f_v1_vr_t01" - Double Agent Evelynn"
		"Hero:hid_commando_016_f_v1_vr_t02" - Double Agent Evelynn"
		"Hero:hid_commando_016_f_v1_vr_t03" - Double Agent Evelynn"
		"Hero:hid_commando_016_f_v1_vr_t04" - Double Agent Evelynn"
		"Hero:hid_commando_016_f_v1_vr_t05" - Double Agent Evelynn"
		"Hero:hid_commando_016_m_v1_sr_t01" - Undercover Vaughn"
		"Hero:hid_commando_016_m_v1_sr_t02" - Undercover Vaughn"
		"Hero:hid_commando_016_m_v1_sr_t03" - Undercover Vaughn"
		"Hero:hid_commando_016_m_v1_sr_t04" - Undercover Vaughn"
		"Hero:hid_commando_016_m_v1_sr_t05" - Undercover Vaughn"
		"Hero:hid_commando_017_f_v1_r_t01" - First Shot Rio"
		"Hero:hid_commando_017_f_v1_r_t02" - First Shot Rio"
		"Hero:hid_commando_017_f_v1_r_t03" - First Shot Rio"
		"Hero:hid_commando_017_f_v1_r_t04" - First Shot Rio"
		"Hero:hid_commando_017_f_v1_sr_t01" - First Shot Rio"
		"Hero:hid_commando_017_f_v1_sr_t02" - First Shot Rio"
		"Hero:hid_commando_017_f_v1_sr_t03" - First Shot Rio"
		"Hero:hid_commando_017_f_v1_sr_t04" - First Shot Rio"
		"Hero:hid_commando_017_f_v1_sr_t05" - First Shot Rio"
		"Hero:hid_commando_017_f_v1_vr_t01" - First Shot Rio"
		"Hero:hid_commando_017_f_v1_vr_t02" - First Shot Rio"
		"Hero:hid_commando_017_f_v1_vr_t03" - First Shot Rio"
		"Hero:hid_commando_017_f_v1_vr_t04" - First Shot Rio"
		"Hero:hid_commando_017_f_v1_vr_t05" - First Shot Rio"
		"Hero:hid_commando_018_sr_t01" - Quickdraw Calamity
		"Hero:hid_commando_018_sr_t02" - Quickdraw Calamity
		"Hero:hid_commando_018_sr_t03" - Quickdraw Calamity
		"Hero:hid_commando_018_sr_t04" - Quickdraw Calamity
		"Hero:hid_commando_018_sr_t05" - Quickdraw Calamity
		"Hero:hid_commando_019_sr_t01" - Steel Wool Carlos"
		"Hero:hid_commando_019_sr_t02" - Steel Wool Carlos"
		"Hero:hid_commando_019_sr_t03" - Steel Wool Carlos"
		"Hero:hid_commando_019_sr_t04" - Steel Wool Carlos"
		"Hero:hid_commando_019_sr_t05" - Steel Wool Carlos"
		"Hero:hid_commando_021_sr_t01" - Liteshow Spitfire
		"Hero:hid_commando_021_sr_t02" - Liteshow Spitfire
		"Hero:hid_commando_021_sr_t03" - Liteshow Spitfire
		"Hero:hid_commando_021_sr_t04" - Liteshow Spitfire
		"Hero:hid_commando_021_sr_t05" - Liteshow Spitfire
		"Hero:hid_commando_022_sr_t01" - Archetype Havoc"
		"Hero:hid_commando_022_sr_t02" - Archetype Havoc"
		"Hero:hid_commando_022_sr_t03" - Archetype Havoc"
		"Hero:hid_commando_022_sr_t04" - Archetype Havoc"
		"Hero:hid_commando_022_sr_t05" - Archetype Havoc"
		"Hero:hid_commando_023_sr_t01" - Jolly Headhunter
		"Hero:hid_commando_023_sr_t02" - Jolly Headhunter
		"Hero:hid_commando_023_sr_t03" - Jolly Headhunter
		"Hero:hid_commando_023_sr_t04" - Jolly Headhunter
		"Hero:hid_commando_023_sr_t05" - Jolly Headhunter
		"Hero:hid_commando_023_vr_t01" - Jolly Headhunter
		"Hero:hid_commando_023_vr_t02" - Jolly Headhunter
		"Hero:hid_commando_023_vr_t03" - Jolly Headhunter
		"Hero:hid_commando_023_vr_t04" - Jolly Headhunter
		"Hero:hid_commando_023_vr_t05" - Jolly Headhunter
		"Hero:hid_commando_024_sr_t01" - Sgt. Winter
		"Hero:hid_commando_024_sr_t02" - Sgt. Winter
		"Hero:hid_commando_024_sr_t03" - Sgt. Winter
		"Hero:hid_commando_024_sr_t04" - Sgt. Winter
		"Hero:hid_commando_024_sr_t05" - Sgt. Winter
		"Hero:hid_commando_024_vr_t01" - Sgt. Winter
		"Hero:hid_commando_024_vr_t02" - Sgt. Winter
		"Hero:hid_commando_024_vr_t03" - Sgt. Winter
		"Hero:hid_commando_024_vr_t04" - Sgt. Winter
		"Hero:hid_commando_024_vr_t05" - Sgt. Winter
		"Hero:hid_commando_025_sr_t01" - Crackshot
		"Hero:hid_commando_025_sr_t02" - Crackshot
		"Hero:hid_commando_025_sr_t03" - Crackshot
		"Hero:hid_commando_025_sr_t04" - Crackshot
		"Hero:hid_commando_025_sr_t05" - Crackshot
		"Hero:hid_commando_026_sr_t01" - Fallen Love Ranger Jonesy
		"Hero:hid_commando_026_sr_t02" - Fallen Love Ranger Jonesy
		"Hero:hid_commando_026_sr_t03" - Fallen Love Ranger Jonesy
		"Hero:hid_commando_026_sr_t04" - Fallen Love Ranger Jonesy
		"Hero:hid_commando_026_sr_t05" - Fallen Love Ranger Jonesy
		"Hero:hid_commando_027_piratesoldier_sr_t01" - Buccaneer Jonesy
		"Hero:hid_commando_027_piratesoldier_sr_t02" - Buccaneer Jonesy
		"Hero:hid_commando_027_piratesoldier_sr_t03" - Buccaneer Jonesy
		"Hero:hid_commando_027_piratesoldier_sr_t04" - Buccaneer Jonesy
		"Hero:hid_commando_027_piratesoldier_sr_t05" - Buccaneer Jonesy
		"Hero:hid_commando_027_piratesoldier_vr_t01" - Buccaneer Jonesy
		"Hero:hid_commando_027_piratesoldier_vr_t02" - Buccaneer Jonesy
		"Hero:hid_commando_027_piratesoldier_vr_t03" - Buccaneer Jonesy
		"Hero:hid_commando_027_piratesoldier_vr_t04" - Buccaneer Jonesy
		"Hero:hid_commando_027_piratesoldier_vr_t05" - Buccaneer Jonesy
		"Hero:hid_commando_028_bunnybrawler_sr_t01" - Bunny Brawler Luna"
		"Hero:hid_commando_028_bunnybrawler_sr_t02" - Bunny Brawler Luna"
		"Hero:hid_commando_028_bunnybrawler_sr_t03" - Bunny Brawler Luna"
		"Hero:hid_commando_028_bunnybrawler_sr_t04" - Bunny Brawler Luna"
		"Hero:hid_commando_028_bunnybrawler_sr_t05" - Bunny Brawler Luna"
		"Hero:hid_commando_029_dinosoldier_sr_t01" - Rex Jonesy
		"Hero:hid_commando_029_dinosoldier_sr_t02" - Rex Jonesy
		"Hero:hid_commando_029_dinosoldier_sr_t03" - Rex Jonesy
		"Hero:hid_commando_029_dinosoldier_sr_t04" - Rex Jonesy
		"Hero:hid_commando_029_dinosoldier_sr_t05" - Rex Jonesy
		"Hero:hid_commando_030_retroscifisoldier_sr_t01" - Extraterrestrial Rio"
		"Hero:hid_commando_030_retroscifisoldier_sr_t02" - Extraterrestrial Rio"
		"Hero:hid_commando_030_retroscifisoldier_sr_t03" - Extraterrestrial Rio"
		"Hero:hid_commando_030_retroscifisoldier_sr_t04" - Extraterrestrial Rio"
		"Hero:hid_commando_030_retroscifisoldier_sr_t05" - Extraterrestrial Rio"
		"Hero:hid_commando_030_retroscifisoldier_vr_t01" - Extraterrestrial Rio"
		"Hero:hid_commando_030_retroscifisoldier_vr_t02" - Extraterrestrial Rio"
		"Hero:hid_commando_030_retroscifisoldier_vr_t03" - Extraterrestrial Rio"
		"Hero:hid_commando_030_retroscifisoldier_vr_t04" - Extraterrestrial Rio"
		"Hero:hid_commando_030_retroscifisoldier_vr_t05" - Extraterrestrial Rio"
		"Hero:hid_commando_031_radsoldier_sr_t01" - Breakbeat Wildcat
		"Hero:hid_commando_031_radsoldier_sr_t02" - Breakbeat Wildcat
		"Hero:hid_commando_031_radsoldier_sr_t03" - Breakbeat Wildcat
		"Hero:hid_commando_031_radsoldier_sr_t04" - Breakbeat Wildcat
		"Hero:hid_commando_031_radsoldier_sr_t05" - Breakbeat Wildcat
		"Hero:hid_commando_031_radsoldier_vr_t01" - Breakbeat Wildcat
		"Hero:hid_commando_031_radsoldier_vr_t02" - Breakbeat Wildcat
		"Hero:hid_commando_031_radsoldier_vr_t03" - Breakbeat Wildcat
		"Hero:hid_commando_031_radsoldier_vr_t04" - Breakbeat Wildcat
		"Hero:hid_commando_031_radsoldier_vr_t05" - Breakbeat Wildcat
		"Hero:hid_commando_032_halloweensoldier_sr_t01" - JONESEE-BOt
		"Hero:hid_commando_032_halloweensoldier_sr_t02" - JONESEE-BOt
		"Hero:hid_commando_032_halloweensoldier_sr_t03" - JONESEE-BOt
		"Hero:hid_commando_032_halloweensoldier_sr_t04" - JONESEE-BOt
		"Hero:hid_commando_032_halloweensoldier_sr_t05" - JONESEE-BOt
		"Hero:hid_commando_033_halloweenquestsoldier_sr_t01" - Swamp Knight
		"Hero:hid_commando_033_halloweenquestsoldier_sr_t02" - Swamp Knight
		"Hero:hid_commando_033_halloweenquestsoldier_sr_t03" - Swamp Knight
		"Hero:hid_commando_033_halloweenquestsoldier_sr_t04" - Swamp Knight
		"Hero:hid_commando_033_halloweenquestsoldier_sr_t05" - Swamp Knight
		"Hero:hid_commando_034_toytinkerer_sr_t01" - Ted"
		"Hero:hid_commando_034_toytinkerer_sr_t02" - Ted"
		"Hero:hid_commando_034_toytinkerer_sr_t03" - Ted"
		"Hero:hid_commando_034_toytinkerer_sr_t04" - Ted"
		"Hero:hid_commando_034_toytinkerer_sr_t05" - Ted"
		"Hero:hid_commando_034_toytinkerer_vr_t01" - Ted"
		"Hero:hid_commando_034_toytinkerer_vr_t02" - Ted"
		"Hero:hid_commando_034_toytinkerer_vr_t03" - Ted"
		"Hero:hid_commando_034_toytinkerer_vr_t04" - Ted"
		"Hero:hid_commando_034_toytinkerer_vr_t05" - Ted"
		"Hero:hid_commando_035_caped_valentine_sr_t01" - Dashing Hawk
		"Hero:hid_commando_035_caped_valentine_sr_t02" - Dashing Hawk
		"Hero:hid_commando_035_caped_valentine_sr_t03" - Dashing Hawk
		"Hero:hid_commando_035_caped_valentine_sr_t04" - Dashing Hawk
		"Hero:hid_commando_035_caped_valentine_sr_t05" - Dashing Hawk
		"Hero:hid_commando_038_shock_wave_sr_t01" - Powerhouse
		"Hero:hid_commando_038_shock_wave_sr_t02" - Powerhouse
		"Hero:hid_commando_038_shock_wave_sr_t03" - Powerhouse
		"Hero:hid_commando_038_shock_wave_sr_t04" - Powerhouse
		"Hero:hid_commando_038_shock_wave_sr_t05" - Powerhouse
		"Hero:hid_commando_038_shock_wave_vr_t01" - Powerhouse
		"Hero:hid_commando_038_shock_wave_vr_t02" - Powerhouse
		"Hero:hid_commando_038_shock_wave_vr_t03" - Powerhouse
		"Hero:hid_commando_038_shock_wave_vr_t04" - Powerhouse
		"Hero:hid_commando_038_shock_wave_vr_t05" - Powerhouse
		"Hero:hid_commando_039_pajama_party_sr_t01" - Tricera Ops Ramirez
		"Hero:hid_commando_039_pajama_party_sr_t02" - Tricera Ops Ramirez
		"Hero:hid_commando_039_pajama_party_sr_t03" - Tricera Ops Ramirez
		"Hero:hid_commando_039_pajama_party_sr_t04" - Tricera Ops Ramirez
		"Hero:hid_commando_039_pajama_party_sr_t05" - Tricera Ops Ramirez
		"Hero:hid_commando_039_pajama_party_vr_t01" - Tricera Ops Ramirez
		"Hero:hid_commando_039_pajama_party_vr_t02" - Tricera Ops Ramirez
		"Hero:hid_commando_039_pajama_party_vr_t03" - Tricera Ops Ramirez
		"Hero:hid_commando_039_pajama_party_vr_t04" - Tricera Ops Ramirez
		"Hero:hid_commando_039_pajama_party_vr_t05" - Tricera Ops Ramirez
		"Hero:hid_commando_040_pirate_br_sr_t01" - Buccaneer Ramirez
		"Hero:hid_commando_040_pirate_br_sr_t02" - Buccaneer Ramirez
		"Hero:hid_commando_040_pirate_br_sr_t03" - Buccaneer Ramirez
		"Hero:hid_commando_040_pirate_br_sr_t04" - Buccaneer Ramirez
		"Hero:hid_commando_040_pirate_br_sr_t05" - Buccaneer Ramirez
		"Hero:hid_commando_040_pirate_br_vr_t01" - Buccaneer Ramirez
		"Hero:hid_commando_040_pirate_br_vr_t02" - Buccaneer Ramirez
		"Hero:hid_commando_040_pirate_br_vr_t03" - Buccaneer Ramirez
		"Hero:hid_commando_040_pirate_br_vr_t04" - Buccaneer Ramirez
		"Hero:hid_commando_040_pirate_br_vr_t05" - Buccaneer Ramirez
		"Hero:hid_commando_041_pirate_02_br_sr_t01" - Sea Wolf Jonesy
		"Hero:hid_commando_041_pirate_02_br_sr_t02" - Sea Wolf Jonesy
		"Hero:hid_commando_041_pirate_02_br_sr_t03" - Sea Wolf Jonesy
		"Hero:hid_commando_041_pirate_02_br_sr_t04" - Sea Wolf Jonesy
		"Hero:hid_commando_041_pirate_02_br_sr_t05" - Sea Wolf Jonesy
		"Hero:hid_commando_041_pirate_02_br_vr_t01" - Sea Wolf Jonesy
		"Hero:hid_commando_041_pirate_02_br_vr_t02" - Sea Wolf Jonesy
		"Hero:hid_commando_041_pirate_02_br_vr_t03" - Sea Wolf Jonesy
		"Hero:hid_commando_041_pirate_02_br_vr_t04" - Sea Wolf Jonesy
		"Hero:hid_commando_041_pirate_02_br_vr_t05" - Sea Wolf Jonesy
		"Hero:hid_commando_042_major_sr_t01" - Major Oswald"
		"Hero:hid_commando_042_major_sr_t02" - Major Oswald"
		"Hero:hid_commando_042_major_sr_t03" - Major Oswald"
		"Hero:hid_commando_042_major_sr_t04" - Major Oswald"
		"Hero:hid_commando_042_major_sr_t05" - Major Oswald"
		"Hero:hid_commando_042_major_vr_t01" - Major Oswald"
		"Hero:hid_commando_042_major_vr_t02" - Major Oswald"
		"Hero:hid_commando_042_major_vr_t03" - Major Oswald"
		"Hero:hid_commando_042_major_vr_t04" - Major Oswald"
		"Hero:hid_commando_042_major_vr_t05" - Major Oswald"
		"Hero:hid_commando_044_gumshoe_dark_sr_t01" - Noir
		"Hero:hid_commando_044_gumshoe_dark_sr_t02" - Noir
		"Hero:hid_commando_044_gumshoe_dark_sr_t03" - Noir
		"Hero:hid_commando_044_gumshoe_dark_sr_t04" - Noir
		"Hero:hid_commando_044_gumshoe_dark_sr_t05" - Noir
		"Hero:hid_commando_044_gumshoe_dark_vr_t01" - Noir
		"Hero:hid_commando_044_gumshoe_dark_vr_t02" - Noir
		"Hero:hid_commando_044_gumshoe_dark_vr_t03" - Noir
		"Hero:hid_commando_044_gumshoe_dark_vr_t04" - Noir
		"Hero:hid_commando_044_gumshoe_dark_vr_t05" - Noir
		"Hero:hid_commando_athena_05" - Rescue Trooper Ramirez
		"Hero:hid_commando_athena_06" - Rescue Trooper Ramirez
		"Hero:hid_commando_athena_12" - Rescue Trooper Ramirez
		"Hero:hid_commando_athena_14" - Rescue Trooper Ramirez
		"Hero:hid_commando_athena_18" - Rescue Trooper Ramirez
		"Hero:hid_commando_athena_22" - Rescue Trooper Ramirez
		"Hero:hid_commando_athena_25" - Rescue Trooper Ramirez
		"Hero:hid_commando_athena_26" - Rescue Trooper Ramirez
		"Hero:hid_commando_gcgrenade_r_t01" - Commando Spitfire
		"Hero:hid_commando_gcgrenade_r_t02" - Commando Spitfire
		"Hero:hid_commando_gcgrenade_r_t03" - Commando Spitfire
		"Hero:hid_commando_gcgrenade_r_t04" - Commando Spitfire
		"Hero:hid_commando_gcgrenade_sr_t01" - Commando Spitfire
		"Hero:hid_commando_gcgrenade_sr_t02" - Commando Spitfire
		"Hero:hid_commando_gcgrenade_sr_t03" - Commando Spitfire
		"Hero:hid_commando_gcgrenade_sr_t04" - Commando Spitfire
		"Hero:hid_commando_gcgrenade_sr_t05" - Commando Spitfire
		"Hero:hid_commando_gcgrenade_t_sr_t01" - Sub Commando Jonesy
		"Hero:hid_commando_gcgrenade_t_sr_t02" - Sub Commando Jonesy
		"Hero:hid_commando_gcgrenade_t_sr_t03" - Sub Commando Jonesy
		"Hero:hid_commando_gcgrenade_t_sr_t04" - Sub Commando Jonesy
		"Hero:hid_commando_gcgrenade_t_sr_t05" - Sub Commando Jonesy
		"Hero:hid_commando_gcgrenade_t_vr_t01" - Sub Commando Jonesy
		"Hero:hid_commando_gcgrenade_t_vr_t02" - Sub Commando Jonesy
		"Hero:hid_commando_gcgrenade_t_vr_t03" - Sub Commando Jonesy
		"Hero:hid_commando_gcgrenade_t_vr_t04" - Sub Commando Jonesy
		"Hero:hid_commando_gcgrenade_t_vr_t05" - Sub Commando Jonesy
		"Hero:hid_commando_gcgrenade_vr_t01" - Commando Spitfire
		"Hero:hid_commando_gcgrenade_vr_t02" - Commando Spitfire
		"Hero:hid_commando_gcgrenade_vr_t03" - Commando Spitfire
		"Hero:hid_commando_gcgrenade_vr_t04" - Commando Spitfire
		"Hero:hid_commando_gcgrenade_vr_t05" - Commando Spitfire
		"Hero:hid_commando_grenadegun_m_t_sr_t01" - Rescue Trooper Havoc"
		"Hero:hid_commando_grenadegun_m_t_sr_t02" - Rescue Trooper Havoc"
		"Hero:hid_commando_grenadegun_m_t_sr_t03" - Rescue Trooper Havoc"
		"Hero:hid_commando_grenadegun_m_t_sr_t04" - Rescue Trooper Havoc"
		"Hero:hid_commando_grenadegun_m_t_sr_t05" - Rescue Trooper Havoc"
		"Hero:hid_commando_grenadegun_r_t01" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_r_t02" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_r_t03" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_r_t04" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_sr_t01" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_sr_t02" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_sr_t03" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_sr_t04" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_sr_t05" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_uc_t01" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_uc_t02" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_uc_t03" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_vr_t01" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_vr_t02" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_vr_t03" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_vr_t04" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenadegun_vr_t05" - Rescue Trooper Ramirez
		"Hero:hid_commando_grenademaster_sr_t01" - Master Grenadier Ramirez
		"Hero:hid_commando_grenademaster_sr_t02" - Master Grenadier Ramirez
		"Hero:hid_commando_grenademaster_sr_t03" - Master Grenadier Ramirez
		"Hero:hid_commando_grenademaster_sr_t04" - Master Grenadier Ramirez
		"Hero:hid_commando_grenademaster_sr_t05" - Master Grenadier Ramirez
		"Hero:hid_commando_gunheadshot_m_v1_roadtrip_sr_t01" - Tactical Assault Sledgehammer
		"Hero:hid_commando_gunheadshot_m_v1_roadtrip_sr_t02" - Tactical Assault Sledgehammer
		"Hero:hid_commando_gunheadshot_m_v1_roadtrip_sr_t03" - Tactical Assault Sledgehammer
		"Hero:hid_commando_gunheadshot_m_v1_roadtrip_sr_t04" - Tactical Assault Sledgehammer
		"Hero:hid_commando_gunheadshot_m_v1_roadtrip_sr_t05" - Tactical Assault Sledgehammer
		"Hero:hid_commando_gunheadshot_sr_t01" - Urban Assault Headhunter
		"Hero:hid_commando_gunheadshot_sr_t02" - Urban Assault Headhunter
		"Hero:hid_commando_gunheadshot_sr_t03" - Urban Assault Headhunter
		"Hero:hid_commando_gunheadshot_sr_t04" - Urban Assault Headhunter
		"Hero:hid_commando_gunheadshot_sr_t05" - Urban Assault Headhunter
		"Hero:hid_commando_gunheadshot_starter_m_sr_t01" - Rogue Agent Jonesy
		"Hero:hid_commando_gunheadshot_starter_m_sr_t02" - Rogue Agent Jonesy
		"Hero:hid_commando_gunheadshot_starter_m_sr_t03" - Rogue Agent Jonesy
		"Hero:hid_commando_gunheadshot_starter_m_sr_t04" - Rogue Agent Jonesy
		"Hero:hid_commando_gunheadshot_starter_m_sr_t05" - Rogue Agent Jonesy
		"Hero:hid_commando_gunheadshot_vr_t01" - Urban Assault Headhunter
		"Hero:hid_commando_gunheadshot_vr_t02" - Urban Assault Headhunter
		"Hero:hid_commando_gunheadshot_vr_t03" - Urban Assault Headhunter
		"Hero:hid_commando_gunheadshot_vr_t04" - Urban Assault Headhunter
		"Hero:hid_commando_gunheadshot_vr_t05" - Urban Assault Headhunter
		"Hero:hid_commando_gunheadshothw_rs01_sr_t01" - Skull Ranger Ramirez
		"Hero:hid_commando_gunheadshothw_rs01_sr_t02" - Skull Ranger Ramirez
		"Hero:hid_commando_gunheadshothw_rs01_sr_t03" - Skull Ranger Ramirez
		"Hero:hid_commando_gunheadshothw_rs01_sr_t04" - Skull Ranger Ramirez
		"Hero:hid_commando_gunheadshothw_rs01_sr_t05" - Skull Ranger Ramirez
		"Hero:hid_commando_gunheadshothw_sr_t01" - Skull Trooper Jonesy
		"Hero:hid_commando_gunheadshothw_sr_t02" - Skull Trooper Jonesy
		"Hero:hid_commando_gunheadshothw_sr_t03" - Skull Trooper Jonesy
		"Hero:hid_commando_gunheadshothw_sr_t04" - Skull Trooper Jonesy
		"Hero:hid_commando_gunheadshothw_sr_t05" - Skull Trooper Jonesy
		"Hero:hid_commando_gunheadshothw_vr_t01" - Skull Trooper Jonesy
		"Hero:hid_commando_gunheadshothw_vr_t02" - Skull Trooper Jonesy
		"Hero:hid_commando_gunheadshothw_vr_t03" - Skull Trooper Jonesy
		"Hero:hid_commando_gunheadshothw_vr_t04" - Skull Trooper Jonesy
		"Hero:hid_commando_gunheadshothw_vr_t05" - Skull Trooper Jonesy
		"Hero:hid_commando_guntough_f_4thjuly_sr_t01" - Star-Spangled Headhunter
		"Hero:hid_commando_guntough_f_4thjuly_sr_t02" - Star-Spangled Headhunter
		"Hero:hid_commando_guntough_f_4thjuly_sr_t03" - Star-Spangled Headhunter
		"Hero:hid_commando_guntough_f_4thjuly_sr_t04" - Star-Spangled Headhunter
		"Hero:hid_commando_guntough_f_4thjuly_sr_t05" - Star-Spangled Headhunter
		"Hero:hid_commando_guntough_m_4thjuly_sr_t01" - Stars and Stripes Jonesy
		"Hero:hid_commando_guntough_m_4thjuly_sr_t02" - Stars and Stripes Jonesy
		"Hero:hid_commando_guntough_m_4thjuly_sr_t03" - Stars and Stripes Jonesy
		"Hero:hid_commando_guntough_m_4thjuly_sr_t04" - Stars and Stripes Jonesy
		"Hero:hid_commando_guntough_m_4thjuly_sr_t05" - Stars and Stripes Jonesy
		"Hero:hid_commando_guntough_r_t01" - Survivalist Jonesy
		"Hero:hid_commando_guntough_r_t02" - Survivalist Jonesy
		"Hero:hid_commando_guntough_r_t03" - Survivalist Jonesy
		"Hero:hid_commando_guntough_r_t04" - Survivalist Jonesy
		"Hero:hid_commando_guntough_rs01_sr_t01" - Birthday Brigade Jonesy
		"Hero:hid_commando_guntough_rs01_sr_t02" - Birthday Brigade Jonesy
		"Hero:hid_commando_guntough_rs01_sr_t03" - Birthday Brigade Jonesy
		"Hero:hid_commando_guntough_rs01_sr_t04" - Birthday Brigade Jonesy
		"Hero:hid_commando_guntough_rs01_sr_t05" - Birthday Brigade Jonesy
		"Hero:hid_commando_guntough_sr_t01" - Survivalist Jonesy
		"Hero:hid_commando_guntough_sr_t02" - Survivalist Jonesy
		"Hero:hid_commando_guntough_sr_t03" - Survivalist Jonesy
		"Hero:hid_commando_guntough_sr_t04" - Survivalist Jonesy
		"Hero:hid_commando_guntough_sr_t05" - Survivalist Jonesy
		"Hero:hid_commando_guntough_uc_t01" - Survivalist Jonesy
		"Hero:hid_commando_guntough_uc_t02" - Survivalist Jonesy
		"Hero:hid_commando_guntough_uc_t03" - Survivalist Jonesy
		"Hero:hid_commando_guntough_valentine_sr_t01" - Love Ranger Jonesy
		"Hero:hid_commando_guntough_valentine_sr_t02" - Love Ranger Jonesy
		"Hero:hid_commando_guntough_valentine_sr_t03" - Love Ranger Jonesy
		"Hero:hid_commando_guntough_valentine_sr_t04" - Love Ranger Jonesy
		"Hero:hid_commando_guntough_valentine_sr_t05" - Love Ranger Jonesy
		"Hero:hid_commando_guntough_vr_t01" - Survivalist Jonesy
		"Hero:hid_commando_guntough_vr_t02" - Survivalist Jonesy
		"Hero:hid_commando_guntough_vr_t03" - Survivalist Jonesy
		"Hero:hid_commando_guntough_vr_t04" - Survivalist Jonesy
		"Hero:hid_commando_guntough_vr_t05" - Survivalist Jonesy
		"Hero:hid_commando_myth02_sr_t01" - Raven"
		"Hero:hid_commando_myth02_sr_t02" - Raven"
		"Hero:hid_commando_myth02_sr_t03" - Raven"
		"Hero:hid_commando_myth02_sr_t04" - Raven"
		"Hero:hid_commando_myth02_sr_t05" - Raven"
		"Hero:hid_commando_myth03_sr_t01" - Carbide
		"Hero:hid_commando_myth03_sr_t02" - Carbide
		"Hero:hid_commando_myth03_sr_t03" - Carbide
		"Hero:hid_commando_myth03_sr_t04" - Carbide
		"Hero:hid_commando_myth03_sr_t05" - Carbide
		"Hero:hid_commando_shockdamage_r_t01" - Shock Trooper Renegade
		"Hero:hid_commando_shockdamage_r_t02" - Shock Trooper Renegade
		"Hero:hid_commando_shockdamage_r_t03" - Shock Trooper Renegade
		"Hero:hid_commando_shockdamage_r_t04" - Shock Trooper Renegade
		"Hero:hid_commando_shockdamage_sr_t01" - Shock Trooper Renegade
		"Hero:hid_commando_shockdamage_sr_t02" - Shock Trooper Renegade
		"Hero:hid_commando_shockdamage_sr_t03" - Shock Trooper Renegade
		"Hero:hid_commando_shockdamage_sr_t04" - Shock Trooper Renegade
		"Hero:hid_commando_shockdamage_sr_t05" - Shock Trooper Renegade
		"Hero:hid_commando_shockdamage_vr_t01" - Shock Trooper Renegade
		"Hero:hid_commando_shockdamage_vr_t02" - Shock Trooper Renegade
		"Hero:hid_commando_shockdamage_vr_t03" - Shock Trooper Renegade
		"Hero:hid_commando_shockdamage_vr_t04" - Shock Trooper Renegade
		"Hero:hid_commando_shockdamage_vr_t05" - Shock Trooper Renegade
		"Hero:hid_commando_sony_r_t01" - Commando Ramirez
		"Hero:hid_commando_sony_r_t02" - Commando Ramirez
		"Hero:hid_commando_sony_r_t03" - Commando Ramirez
		"Hero:hid_commando_sony_r_t04" - Commando Ramirez
		"Hero:hid_commando_sony_sr_t01" - Commando Ramirez
		"Hero:hid_commando_sony_sr_t02" - Commando Ramirez
		"Hero:hid_commando_sony_sr_t03" - Commando Ramirez
		"Hero:hid_commando_sony_sr_t04" - Commando Ramirez
		"Hero:hid_commando_sony_sr_t05" - Commando Ramirez
		"Hero:hid_commando_sony_vr_t01" - Commando Ramirez
		"Hero:hid_commando_sony_vr_t02" - Commando Ramirez
		"Hero:hid_commando_sony_vr_t03" - Commando Ramirez
		"Hero:hid_commando_sony_vr_t04" - Commando Ramirez
		"Hero:hid_commando_sony_vr_t05" - Commando Ramirez
		"Hero:hid_commando_xbox_r_t01" - Commando Renegade
		"Hero:hid_commando_xbox_r_t02" - Commando Renegade
		"Hero:hid_commando_xbox_r_t03" - Commando Renegade
		"Hero:hid_commando_xbox_r_t04" - Commando Renegade
		"Hero:hid_commando_xbox_sr_t01" - Commando Renegade
		"Hero:hid_commando_xbox_sr_t02" - Commando Renegade
		"Hero:hid_commando_xbox_sr_t03" - Commando Renegade
		"Hero:hid_commando_xbox_sr_t04" - Commando Renegade
		"Hero:hid_commando_xbox_sr_t05" - Commando Renegade
		"Hero:hid_commando_xbox_vr_t01" - Commando Renegade
		"Hero:hid_commando_xbox_vr_t02" - Commando Renegade
		"Hero:hid_commando_xbox_vr_t03" - Commando Renegade
		"Hero:hid_commando_xbox_vr_t04" - Commando Renegade
		"Hero:hid_commando_xbox_vr_t05" - Commando Renegade


	CONSTRUCTORS:
		"Hero:hid_constructor_007_r_t01" - Controller Harper
		"Hero:hid_constructor_007_r_t02" - Controller Harper
		"Hero:hid_constructor_007_r_t03" - Controller Harper
		"Hero:hid_constructor_007_r_t04" - Controller Harper
		"Hero:hid_constructor_007_sr_t01" - Controller Harper
		"Hero:hid_constructor_007_sr_t02" - Controller Harper
		"Hero:hid_constructor_007_sr_t03" - Controller Harper
		"Hero:hid_constructor_007_sr_t04" - Controller Harper
		"Hero:hid_constructor_007_sr_t05" - Controller Harper
		"Hero:hid_constructor_007_uc_t01" - Controller Harper
		"Hero:hid_constructor_007_uc_t02" - Controller Harper
		"Hero:hid_constructor_007_uc_t03" - Controller Harper
		"Hero:hid_constructor_007_vr_t01" - Controller Harper
		"Hero:hid_constructor_007_vr_t02" - Controller Harper
		"Hero:hid_constructor_007_vr_t03" - Controller Harper
		"Hero:hid_constructor_007_vr_t04" - Controller Harper
		"Hero:hid_constructor_007_vr_t05" - Controller Harper
		"Hero:hid_constructor_007hw_sr_t01" - Kyle the 13th"
		"Hero:hid_constructor_007hw_sr_t02" - Kyle the 13th"
		"Hero:hid_constructor_007hw_sr_t03" - Kyle the 13th"
		"Hero:hid_constructor_007hw_sr_t04" - Kyle the 13th"
		"Hero:hid_constructor_007hw_sr_t05" - Kyle the 13th"
		"Hero:hid_constructor_007hw_vr_t01" - Kyle the 13th"
		"Hero:hid_constructor_007hw_vr_t02" - Kyle the 13th"
		"Hero:hid_constructor_007hw_vr_t03" - Kyle the 13th"
		"Hero:hid_constructor_007hw_vr_t04" - Kyle the 13th"
		"Hero:hid_constructor_007hw_vr_t05" - Kyle the 13th"
		"Hero:hid_constructor_008_foundersf_sr_t01" - Power B.A.S.E. Penny
		"Hero:hid_constructor_008_foundersf_sr_t02" - Power B.A.S.E. Penny
		"Hero:hid_constructor_008_foundersf_sr_t03" - Power B.A.S.E. Penny
		"Hero:hid_constructor_008_foundersf_sr_t04" - Power B.A.S.E. Penny
		"Hero:hid_constructor_008_foundersf_sr_t05" - Power B.A.S.E. Penny
		"Hero:hid_constructor_008_foundersm_sr_t01" - Power B.A.S.E. Kyle
		"Hero:hid_constructor_008_foundersm_sr_t02" - Power B.A.S.E. Kyle
		"Hero:hid_constructor_008_foundersm_sr_t03" - Power B.A.S.E. Kyle
		"Hero:hid_constructor_008_foundersm_sr_t04" - Power B.A.S.E. Kyle
		"Hero:hid_constructor_008_foundersm_sr_t05" - Power B.A.S.E. Kyle
		"Hero:hid_constructor_008_r_t01" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_008_r_t02" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_008_r_t03" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_008_r_t04" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_008_sr_t01" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_008_sr_t02" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_008_sr_t03" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_008_sr_t04" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_008_sr_t05" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_008_vr_t01" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_008_vr_t02" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_008_vr_t03" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_008_vr_t04" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_008_vr_t05" - Power B.A.S.E. Knox"
		"Hero:hid_constructor_009_r_t01" - Sentinel Hype
		"Hero:hid_constructor_009_r_t02" - Sentinel Hype
		"Hero:hid_constructor_009_r_t03" - Sentinel Hype
		"Hero:hid_constructor_009_r_t04" - Sentinel Hype
		"Hero:hid_constructor_009_sr_t01" - Sentinel Hype
		"Hero:hid_constructor_009_sr_t02" - Sentinel Hype
		"Hero:hid_constructor_009_sr_t03" - Sentinel Hype
		"Hero:hid_constructor_009_sr_t04" - Sentinel Hype
		"Hero:hid_constructor_009_sr_t05" - Sentinel Hype
		"Hero:hid_constructor_009_vr_t01" - Sentinel Hype
		"Hero:hid_constructor_009_vr_t02" - Sentinel Hype
		"Hero:hid_constructor_009_vr_t03" - Sentinel Hype
		"Hero:hid_constructor_009_vr_t04" - Sentinel Hype
		"Hero:hid_constructor_009_vr_t05" - Sentinel Hype
		"Hero:hid_constructor_010_sr_t01" - Guardian Bull"
		"Hero:hid_constructor_010_sr_t02" - Guardian Bull"
		"Hero:hid_constructor_010_sr_t03" - Guardian Bull"
		"Hero:hid_constructor_010_sr_t04" - Guardian Bull"
		"Hero:hid_constructor_010_sr_t05" - Guardian Bull"
		"Hero:hid_constructor_010_vr_t01" - Guardian Bull"
		"Hero:hid_constructor_010_vr_t02" - Guardian Bull"
		"Hero:hid_constructor_010_vr_t03" - Guardian Bull"
		"Hero:hid_constructor_010_vr_t04" - Guardian Bull"
		"Hero:hid_constructor_010_vr_t05" - Guardian Bull"
		"Hero:hid_constructor_011_f_v1_roadtrip_sr_t01" - Thunder Thora"
		"Hero:hid_constructor_011_f_v1_roadtrip_sr_t02" - Thunder Thora"
		"Hero:hid_constructor_011_f_v1_roadtrip_sr_t03" - Thunder Thora"
		"Hero:hid_constructor_011_f_v1_roadtrip_sr_t04" - Thunder Thora"
		"Hero:hid_constructor_011_f_v1_roadtrip_sr_t05" - Thunder Thora"
		"Hero:hid_constructor_011_r_t01" - Machinist Harper
		"Hero:hid_constructor_011_r_t02" - Machinist Harper
		"Hero:hid_constructor_011_r_t03" - Machinist Harper
		"Hero:hid_constructor_011_r_t04" - Machinist Harper
		"Hero:hid_constructor_011_sr_t01" - Machinist Harper
		"Hero:hid_constructor_011_sr_t02" - Machinist Harper
		"Hero:hid_constructor_011_sr_t03" - Machinist Harper
		"Hero:hid_constructor_011_sr_t04" - Machinist Harper
		"Hero:hid_constructor_011_sr_t05" - Machinist Harper
		"Hero:hid_constructor_011_vr_t01" - Machinist Harper
		"Hero:hid_constructor_011_vr_t02" - Machinist Harper
		"Hero:hid_constructor_011_vr_t03" - Machinist Harper
		"Hero:hid_constructor_011_vr_t04" - Machinist Harper
		"Hero:hid_constructor_011_vr_t05" - Machinist Harper
		"Hero:hid_constructor_013_r_t01" - Warden Kyle
		"Hero:hid_constructor_013_r_t02" - Warden Kyle
		"Hero:hid_constructor_013_r_t03" - Warden Kyle
		"Hero:hid_constructor_013_r_t04" - Warden Kyle
		"Hero:hid_constructor_013_sr_t01" - Warden Kyle
		"Hero:hid_constructor_013_sr_t02" - Warden Kyle
		"Hero:hid_constructor_013_sr_t03" - Warden Kyle
		"Hero:hid_constructor_013_sr_t04" - Warden Kyle
		"Hero:hid_constructor_013_sr_t05" - Warden Kyle
		"Hero:hid_constructor_013_uc_t01" - Warden Kyle
		"Hero:hid_constructor_013_uc_t02" - Warden Kyle
		"Hero:hid_constructor_013_uc_t03" - Warden Kyle
		"Hero:hid_constructor_013_vr_t01" - Warden Kyle
		"Hero:hid_constructor_013_vr_t02" - Warden Kyle
		"Hero:hid_constructor_013_vr_t03" - Warden Kyle
		"Hero:hid_constructor_013_vr_t04" - Warden Kyle
		"Hero:hid_constructor_013_vr_t05" - Warden Kyle
		"Hero:hid_constructor_014_f_sr_t01" - Riot Control Izza"
		"Hero:hid_constructor_014_f_sr_t02" - Riot Control Izza"
		"Hero:hid_constructor_014_f_sr_t03" - Riot Control Izza"
		"Hero:hid_constructor_014_f_sr_t04" - Riot Control Izza"
		"Hero:hid_constructor_014_f_sr_t05" - Riot Control Izza"
		"Hero:hid_constructor_014_r_t01" - Riot Response Hazard"
		"Hero:hid_constructor_014_r_t02" - Riot Response Hazard"
		"Hero:hid_constructor_014_r_t03" - Riot Response Hazard"
		"Hero:hid_constructor_014_r_t04" - Riot Response Hazard"
		"Hero:hid_constructor_014_sr_t01" - Riot Response Hazard"
		"Hero:hid_constructor_014_sr_t02" - Riot Response Hazard"
		"Hero:hid_constructor_014_sr_t03" - Riot Response Hazard"
		"Hero:hid_constructor_014_sr_t04" - Riot Response Hazard"
		"Hero:hid_constructor_014_sr_t05" - Riot Response Hazard"
		"Hero:hid_constructor_014_vr_t01" - Riot Response Hazard"
		"Hero:hid_constructor_014_vr_t02" - Riot Response Hazard"
		"Hero:hid_constructor_014_vr_t03" - Riot Response Hazard"
		"Hero:hid_constructor_014_vr_t04" - Riot Response Hazard"
		"Hero:hid_constructor_014_vr_t05" - Riot Response Hazard"
		"Hero:hid_constructor_015_r_t01" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_015_r_t02" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_015_r_t03" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_015_r_t04" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_015_sr_t01" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_015_sr_t02" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_015_sr_t03" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_015_sr_t04" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_015_sr_t05" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_015_vr_t01" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_015_vr_t02" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_015_vr_t03" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_015_vr_t04" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_015_vr_t05" - Heavy B.A.S.E. Kyle
		"Hero:hid_constructor_016_f_v1_sr_t01" - Demolitionist Penny
		"Hero:hid_constructor_016_f_v1_sr_t02" - Demolitionist Penny
		"Hero:hid_constructor_016_f_v1_sr_t03" - Demolitionist Penny
		"Hero:hid_constructor_016_f_v1_sr_t04" - Demolitionist Penny
		"Hero:hid_constructor_016_f_v1_sr_t05" - Demolitionist Penny
		"Hero:hid_constructor_016_f_v1_vr_t01" - Demolitionist Penny
		"Hero:hid_constructor_016_f_v1_vr_t02" - Demolitionist Penny
		"Hero:hid_constructor_016_f_v1_vr_t03" - Demolitionist Penny
		"Hero:hid_constructor_016_f_v1_vr_t04" - Demolitionist Penny
		"Hero:hid_constructor_016_f_v1_vr_t05" - Demolitionist Penny
		"Hero:hid_constructor_016_m_v1_blockbuster_sr_t01" - 8-Bit Demo"
		"Hero:hid_constructor_016_m_v1_blockbuster_sr_t02" - 8-Bit Demo"
		"Hero:hid_constructor_016_m_v1_blockbuster_sr_t03" - 8-Bit Demo"
		"Hero:hid_constructor_016_m_v1_blockbuster_sr_t04" - 8-Bit Demo"
		"Hero:hid_constructor_016_m_v1_blockbuster_sr_t05" - 8-Bit Demo"
		"Hero:hid_constructor_016_m_v1_sr_t01" - Saboteur Bull"
		"Hero:hid_constructor_016_m_v1_sr_t02" - Saboteur Bull"
		"Hero:hid_constructor_016_m_v1_sr_t03" - Saboteur Bull"
		"Hero:hid_constructor_016_m_v1_sr_t04" - Saboteur Bull"
		"Hero:hid_constructor_016_m_v1_sr_t05" - Saboteur Bull"
		"Hero:hid_constructor_017_f_v1_r_t01" - Vintage-Tech Penny
		"Hero:hid_constructor_017_f_v1_r_t02" - Vintage-Tech Penny
		"Hero:hid_constructor_017_f_v1_r_t03" - Vintage-Tech Penny
		"Hero:hid_constructor_017_f_v1_r_t04" - Vintage-Tech Penny
		"Hero:hid_constructor_017_f_v1_sr_t01" - Vintage-Tech Penny
		"Hero:hid_constructor_017_f_v1_sr_t02" - Vintage-Tech Penny
		"Hero:hid_constructor_017_f_v1_sr_t03" - Vintage-Tech Penny
		"Hero:hid_constructor_017_f_v1_sr_t04" - Vintage-Tech Penny
		"Hero:hid_constructor_017_f_v1_sr_t05" - Vintage-Tech Penny
		"Hero:hid_constructor_017_f_v1_vr_t01" - Vintage-Tech Penny
		"Hero:hid_constructor_017_f_v1_vr_t02" - Vintage-Tech Penny
		"Hero:hid_constructor_017_f_v1_vr_t03" - Vintage-Tech Penny
		"Hero:hid_constructor_017_f_v1_vr_t04" - Vintage-Tech Penny
		"Hero:hid_constructor_017_f_v1_vr_t05" - Vintage-Tech Penny
		"Hero:hid_constructor_018_sr_t01" - Black Knight Garridan"
		"Hero:hid_constructor_018_sr_t02" - Black Knight Garridan"
		"Hero:hid_constructor_018_sr_t03" - Black Knight Garridan"
		"Hero:hid_constructor_018_sr_t04" - Black Knight Garridan"
		"Hero:hid_constructor_018_sr_t05" - Black Knight Garridan"
		"Hero:hid_constructor_019_sr_t01" - Sentry Gunner Airheart
		"Hero:hid_constructor_019_sr_t02" - Sentry Gunner Airheart
		"Hero:hid_constructor_019_sr_t03" - Sentry Gunner Airheart
		"Hero:hid_constructor_019_sr_t04" - Sentry Gunner Airheart
		"Hero:hid_constructor_019_sr_t05" - Sentry Gunner Airheart
		"Hero:hid_constructor_020_sr_t01" - Sentry Gunner Krampus"
		"Hero:hid_constructor_020_sr_t02" - Sentry Gunner Krampus"
		"Hero:hid_constructor_020_sr_t03" - Sentry Gunner Krampus"
		"Hero:hid_constructor_020_sr_t04" - Sentry Gunner Krampus"
		"Hero:hid_constructor_020_sr_t05" - Sentry Gunner Krampus"
		"Hero:hid_constructor_021_sr_t01" - Dark Vanguard Airheart
		"Hero:hid_constructor_021_sr_t02" - Dark Vanguard Airheart
		"Hero:hid_constructor_021_sr_t03" - Dark Vanguard Airheart
		"Hero:hid_constructor_021_sr_t04" - Dark Vanguard Airheart
		"Hero:hid_constructor_021_sr_t05" - Dark Vanguard Airheart
		"Hero:hid_constructor_022_sr_t01" - Conqueror Magnus"
		"Hero:hid_constructor_022_sr_t02" - Conqueror Magnus"
		"Hero:hid_constructor_022_sr_t03" - Conqueror Magnus"
		"Hero:hid_constructor_022_sr_t04" - Conqueror Magnus"
		"Hero:hid_constructor_022_sr_t05" - Conqueror Magnus"
		"Hero:hid_constructor_023_sr_t01" - The Ice King"
		"Hero:hid_constructor_023_sr_t02" - The Ice King"
		"Hero:hid_constructor_023_sr_t03" - The Ice King"
		"Hero:hid_constructor_023_sr_t04" - The Ice King"
		"Hero:hid_constructor_023_sr_t05" - The Ice King"
		"Hero:hid_constructor_024_pirateconstructor_sr_t01" - Privateer Hype
		"Hero:hid_constructor_024_pirateconstructor_sr_t02" - Privateer Hype
		"Hero:hid_constructor_024_pirateconstructor_sr_t03" - Privateer Hype
		"Hero:hid_constructor_024_pirateconstructor_sr_t04" - Privateer Hype
		"Hero:hid_constructor_024_pirateconstructor_sr_t05" - Privateer Hype
		"Hero:hid_constructor_024_pirateconstructor_vr_t01" - Privateer Hype
		"Hero:hid_constructor_024_pirateconstructor_vr_t02" - Privateer Hype
		"Hero:hid_constructor_024_pirateconstructor_vr_t03" - Privateer Hype
		"Hero:hid_constructor_024_pirateconstructor_vr_t04" - Privateer Hype
		"Hero:hid_constructor_024_pirateconstructor_vr_t05" - Privateer Hype
		"Hero:hid_constructor_025_progressivepirateconstructor_sr_t01" - Blakebeard The Blackhearted"
		"Hero:hid_constructor_025_progressivepirateconstructor_sr_t02" - Blakebeard The Blackhearted"
		"Hero:hid_constructor_025_progressivepirateconstructor_sr_t03" - Blakebeard The Blackhearted"
		"Hero:hid_constructor_025_progressivepirateconstructor_sr_t04" - Blakebeard The Blackhearted"
		"Hero:hid_constructor_025_progressivepirateconstructor_sr_t05" - Blakebeard The Blackhearted"
		"Hero:hid_constructor_026_bombsquadconstructor_sr_t01" - BombSquad Kyle
		"Hero:hid_constructor_026_bombsquadconstructor_sr_t02" - BombSquad Kyle
		"Hero:hid_constructor_026_bombsquadconstructor_sr_t03" - BombSquad Kyle
		"Hero:hid_constructor_026_bombsquadconstructor_sr_t04" - BombSquad Kyle
		"Hero:hid_constructor_026_bombsquadconstructor_sr_t05" - BombSquad Kyle
		"Hero:hid_constructor_026_bombsquadconstructor_vr_t01" - BombSquad Kyle
		"Hero:hid_constructor_026_bombsquadconstructor_vr_t02" - BombSquad Kyle
		"Hero:hid_constructor_026_bombsquadconstructor_vr_t03" - BombSquad Kyle
		"Hero:hid_constructor_026_bombsquadconstructor_vr_t04" - BombSquad Kyle
		"Hero:hid_constructor_026_bombsquadconstructor_vr_t05" - BombSquad Kyle
		"Hero:hid_constructor_027_dinoconstructor_sr_t01" - Prehistoric Izza"
		"Hero:hid_constructor_027_dinoconstructor_sr_t02" - Prehistoric Izza"
		"Hero:hid_constructor_027_dinoconstructor_sr_t03" - Prehistoric Izza"
		"Hero:hid_constructor_027_dinoconstructor_sr_t04" - Prehistoric Izza"
		"Hero:hid_constructor_027_dinoconstructor_sr_t05" - Prehistoric Izza"
		"Hero:hid_constructor_028_retroscificonstructor_sr_t01" - ED-Ee
		"Hero:hid_constructor_028_retroscificonstructor_sr_t02" - ED-Ee
		"Hero:hid_constructor_028_retroscificonstructor_sr_t03" - ED-Ee
		"Hero:hid_constructor_028_retroscificonstructor_sr_t04" - ED-Ee
		"Hero:hid_constructor_028_retroscificonstructor_sr_t05" - ED-Ee
		"Hero:hid_constructor_028_retroscificonstructor_vr_t01" - ED-Ee
		"Hero:hid_constructor_028_retroscificonstructor_vr_t02" - ED-Ee
		"Hero:hid_constructor_028_retroscificonstructor_vr_t03" - ED-Ee
		"Hero:hid_constructor_028_retroscificonstructor_vr_t04" - ED-Ee
		"Hero:hid_constructor_028_retroscificonstructor_vr_t05" - ED-Ee
		"Hero:hid_constructor_029_radstoryconstructor_sr_t01" - Dennis Jr."
		"Hero:hid_constructor_029_radstoryconstructor_sr_t02" - Dennis Jr."
		"Hero:hid_constructor_029_radstoryconstructor_sr_t03" - Dennis Jr."
		"Hero:hid_constructor_029_radstoryconstructor_sr_t04" - Dennis Jr."
		"Hero:hid_constructor_029_radstoryconstructor_sr_t05" - Dennis Jr."
		"Hero:hid_constructor_030_radconstructor_sr_t01" - Power Pop Penny
		"Hero:hid_constructor_030_radconstructor_sr_t02" - Power Pop Penny
		"Hero:hid_constructor_030_radconstructor_sr_t03" - Power Pop Penny
		"Hero:hid_constructor_030_radconstructor_sr_t04" - Power Pop Penny
		"Hero:hid_constructor_030_radconstructor_sr_t05" - Power Pop Penny
		"Hero:hid_constructor_030_radconstructor_vr_t01" - Power Pop Penny
		"Hero:hid_constructor_030_radconstructor_vr_t02" - Power Pop Penny
		"Hero:hid_constructor_030_radconstructor_vr_t03" - Power Pop Penny
		"Hero:hid_constructor_030_radconstructor_vr_t04" - Power Pop Penny
		"Hero:hid_constructor_030_radconstructor_vr_t05" - Power Pop Penny
		"Hero:hid_constructor_031_halloweenconstructor_sr_t01" - \"Arrlene\" Izza"
		"Hero:hid_constructor_031_halloweenconstructor_sr_t02" - \"Arrlene\" Izza"
		"Hero:hid_constructor_031_halloweenconstructor_sr_t03" - \"Arrlene\" Izza"
		"Hero:hid_constructor_031_halloweenconstructor_sr_t04" - \"Arrlene\" Izza"
		"Hero:hid_constructor_031_halloweenconstructor_sr_t05" - \"Arrlene\" Izza"
		"Hero:hid_constructor_032_toyconstructor_sr_t01" - Sgt. Tank Gatling"
		"Hero:hid_constructor_032_toyconstructor_sr_t02" - Sgt. Tank Gatling"
		"Hero:hid_constructor_032_toyconstructor_sr_t03" - Sgt. Tank Gatling"
		"Hero:hid_constructor_032_toyconstructor_sr_t04" - Sgt. Tank Gatling"
		"Hero:hid_constructor_032_toyconstructor_sr_t05" - Sgt. Tank Gatling"
		"Hero:hid_constructor_032_toyconstructor_vr_t01" - Sgt. Tank Gatling"
		"Hero:hid_constructor_032_toyconstructor_vr_t02" - Sgt. Tank Gatling"
		"Hero:hid_constructor_032_toyconstructor_vr_t03" - Sgt. Tank Gatling"
		"Hero:hid_constructor_032_toyconstructor_vr_t04" - Sgt. Tank Gatling"
		"Hero:hid_constructor_032_toyconstructor_vr_t05" - Sgt. Tank Gatling"
		"Hero:hid_constructor_033_villain_fleming_sr_t01" - Gold Knox"
		"Hero:hid_constructor_033_villain_fleming_sr_t02" - Gold Knox"
		"Hero:hid_constructor_033_villain_fleming_sr_t03" - Gold Knox"
		"Hero:hid_constructor_033_villain_fleming_sr_t04" - Gold Knox"
		"Hero:hid_constructor_033_villain_fleming_sr_t05" - Gold Knox"
		"Hero:hid_constructor_033_villain_fleming_vr_t01" - Gold Knox"
		"Hero:hid_constructor_033_villain_fleming_vr_t02" - Gold Knox"
		"Hero:hid_constructor_033_villain_fleming_vr_t03" - Gold Knox"
		"Hero:hid_constructor_033_villain_fleming_vr_t04" - Gold Knox"
		"Hero:hid_constructor_033_villain_fleming_vr_t05" - Gold Knox"
		"Hero:hid_constructor_034_mechstructor_sr_t01" - Machinist Mina"
		"Hero:hid_constructor_034_mechstructor_sr_t02" - Machinist Mina"
		"Hero:hid_constructor_034_mechstructor_sr_t03" - Machinist Mina"
		"Hero:hid_constructor_034_mechstructor_sr_t04" - Machinist Mina"
		"Hero:hid_constructor_034_mechstructor_sr_t05" - Machinist Mina"
		"Hero:hid_constructor_034_mechstructor_vr_t01" - Machinist Mina"
		"Hero:hid_constructor_034_mechstructor_vr_t02" - Machinist Mina"
		"Hero:hid_constructor_034_mechstructor_vr_t03" - Machinist Mina"
		"Hero:hid_constructor_034_mechstructor_vr_t04" - Machinist Mina"
		"Hero:hid_constructor_034_mechstructor_vr_t05" - Machinist Mina"
		"Hero:hid_constructor_035_birthday_constructor_sr_t01" - Birthday Brigade Penny
		"Hero:hid_constructor_035_birthday_constructor_sr_t02" - Birthday Brigade Penny
		"Hero:hid_constructor_035_birthday_constructor_sr_t03" - Birthday Brigade Penny
		"Hero:hid_constructor_035_birthday_constructor_sr_t04" - Birthday Brigade Penny
		"Hero:hid_constructor_035_birthday_constructor_sr_t05" - Birthday Brigade Penny
		"Hero:hid_constructor_035_birthday_constructor_vr_t01" - Birthday Brigade Penny
		"Hero:hid_constructor_035_birthday_constructor_vr_t02" - Birthday Brigade Penny
		"Hero:hid_constructor_035_birthday_constructor_vr_t03" - Birthday Brigade Penny
		"Hero:hid_constructor_035_birthday_constructor_vr_t04" - Birthday Brigade Penny
		"Hero:hid_constructor_035_birthday_constructor_vr_t05" - Birthday Brigade Penny
		"Hero:hid_constructor_036_dino_constructor_sr_t01" - Ankylo Kyle
		"Hero:hid_constructor_036_dino_constructor_sr_t02" - Ankylo Kyle
		"Hero:hid_constructor_036_dino_constructor_sr_t03" - Ankylo Kyle
		"Hero:hid_constructor_036_dino_constructor_sr_t04" - Ankylo Kyle
		"Hero:hid_constructor_036_dino_constructor_sr_t05" - Ankylo Kyle
		"Hero:hid_constructor_036_dino_constructor_vr_t01" - Ankylo Kyle
		"Hero:hid_constructor_036_dino_constructor_vr_t02" - Ankylo Kyle
		"Hero:hid_constructor_036_dino_constructor_vr_t03" - Ankylo Kyle
		"Hero:hid_constructor_036_dino_constructor_vr_t04" - Ankylo Kyle
		"Hero:hid_constructor_036_dino_constructor_vr_t05" - Ankylo Kyle
		"Hero:hid_constructor_037_director_sr_t01" - Director Riggs"
		"Hero:hid_constructor_037_director_sr_t02" - Director Riggs"
		"Hero:hid_constructor_037_director_sr_t03" - Director Riggs"
		"Hero:hid_constructor_037_director_sr_t04" - Director Riggs"
		"Hero:hid_constructor_037_director_sr_t05" - Director Riggs"
		"Hero:hid_constructor_037_director_vr_t01" - Director Riggs"
		"Hero:hid_constructor_037_director_vr_t02" - Director Riggs"
		"Hero:hid_constructor_037_director_vr_t03" - Director Riggs"
		"Hero:hid_constructor_037_director_vr_t04" - Director Riggs"
		"Hero:hid_constructor_037_director_vr_t05" - Director Riggs"
		"Hero:hid_constructor_038_gumshoe_sr_t01" - Sleuth"
		"Hero:hid_constructor_038_gumshoe_sr_t02" - Sleuth"
		"Hero:hid_constructor_038_gumshoe_sr_t03" - Sleuth"
		"Hero:hid_constructor_038_gumshoe_sr_t04" - Sleuth"
		"Hero:hid_constructor_038_gumshoe_sr_t05" - Sleuth"
		"Hero:hid_constructor_038_gumshoe_vr_t01" - Sleuth"
		"Hero:hid_constructor_038_gumshoe_vr_t02" - Sleuth"
		"Hero:hid_constructor_038_gumshoe_vr_t03" - Sleuth"
		"Hero:hid_constructor_038_gumshoe_vr_t04" - Sleuth"
		"Hero:hid_constructor_038_gumshoe_vr_t05" - Sleuth"
		"Hero:hid_constructor_basebig_sr_t01" - MEGA B.A.S.E. Kyle
		"Hero:hid_constructor_basebig_sr_t02" - MEGA B.A.S.E. Kyle
		"Hero:hid_constructor_basebig_sr_t03" - MEGA B.A.S.E. Kyle
		"Hero:hid_constructor_basebig_sr_t04" - MEGA B.A.S.E. Kyle
		"Hero:hid_constructor_basebig_sr_t05" - MEGA B.A.S.E. Kyle
		"Hero:hid_constructor_basehyper_r_t01" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyper_r_t02" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyper_r_t03" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyper_r_t04" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyper_sr_t01" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyper_sr_t02" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyper_sr_t03" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyper_sr_t04" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyper_sr_t05" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyper_vr_t01" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyper_vr_t02" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyper_vr_t03" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyper_vr_t04" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyper_vr_t05" - Hotfixer Hazard"
		"Hero:hid_constructor_basehyperhw_sr_t01" - Catstructor Penny
		"Hero:hid_constructor_basehyperhw_sr_t02" - Catstructor Penny
		"Hero:hid_constructor_basehyperhw_sr_t03" - Catstructor Penny
		"Hero:hid_constructor_basehyperhw_sr_t04" - Catstructor Penny
		"Hero:hid_constructor_basehyperhw_sr_t05" - Catstructor Penny
		"Hero:hid_constructor_basehyperhw_vr_t01" - Catstructor Penny
		"Hero:hid_constructor_basehyperhw_vr_t02" - Catstructor Penny
		"Hero:hid_constructor_basehyperhw_vr_t03" - Catstructor Penny
		"Hero:hid_constructor_basehyperhw_vr_t04" - Catstructor Penny
		"Hero:hid_constructor_basehyperhw_vr_t05" - Catstructor Penny
		"Hero:hid_constructor_hammerplasma_4thjuly_sr_t01" - Patriot Penny
		"Hero:hid_constructor_hammerplasma_4thjuly_sr_t02" - Patriot Penny
		"Hero:hid_constructor_hammerplasma_4thjuly_sr_t03" - Patriot Penny
		"Hero:hid_constructor_hammerplasma_4thjuly_sr_t04" - Patriot Penny
		"Hero:hid_constructor_hammerplasma_4thjuly_sr_t05" - Patriot Penny
		"Hero:hid_constructor_hammerplasma_sr_t01" - Electro-pulse Penny
		"Hero:hid_constructor_hammerplasma_sr_t02" - Electro-pulse Penny
		"Hero:hid_constructor_hammerplasma_sr_t03" - Electro-pulse Penny
		"Hero:hid_constructor_hammerplasma_sr_t04" - Electro-pulse Penny
		"Hero:hid_constructor_hammerplasma_sr_t05" - Electro-pulse Penny
		"Hero:hid_constructor_hammerplasma_vr_t01" - Electro-pulse Penny
		"Hero:hid_constructor_hammerplasma_vr_t02" - Electro-pulse Penny
		"Hero:hid_constructor_hammerplasma_vr_t03" - Electro-pulse Penny
		"Hero:hid_constructor_hammerplasma_vr_t04" - Electro-pulse Penny
		"Hero:hid_constructor_hammerplasma_vr_t05" - Electro-pulse Penny
		"Hero:hid_constructor_hammertank_r_t01" - Tank Penny
		"Hero:hid_constructor_hammertank_r_t02" - Tank Penny
		"Hero:hid_constructor_hammertank_r_t03" - Tank Penny
		"Hero:hid_constructor_hammertank_r_t04" - Tank Penny
		"Hero:hid_constructor_hammertank_sr_t01" - Tank Penny
		"Hero:hid_constructor_hammertank_sr_t02" - Tank Penny
		"Hero:hid_constructor_hammertank_sr_t03" - Tank Penny
		"Hero:hid_constructor_hammertank_sr_t04" - Tank Penny
		"Hero:hid_constructor_hammertank_sr_t05" - Tank Penny
		"Hero:hid_constructor_hammertank_uc_t01" - Tank Penny
		"Hero:hid_constructor_hammertank_uc_t02" - Tank Penny
		"Hero:hid_constructor_hammertank_uc_t03" - Tank Penny
		"Hero:hid_constructor_hammertank_vr_t01" - Tank Penny
		"Hero:hid_constructor_hammertank_vr_t02" - Tank Penny
		"Hero:hid_constructor_hammertank_vr_t03" - Tank Penny
		"Hero:hid_constructor_hammertank_vr_t04" - Tank Penny
		"Hero:hid_constructor_hammertank_vr_t05" - Tank Penny
		"Hero:hid_constructor_myth02_sr_t01" - Steel Wool Syd"
		"Hero:hid_constructor_myth02_sr_t02" - Steel Wool Syd"
		"Hero:hid_constructor_myth02_sr_t03" - Steel Wool Syd"
		"Hero:hid_constructor_myth02_sr_t04" - Steel Wool Syd"
		"Hero:hid_constructor_myth02_sr_t05" - Steel Wool Syd"
		"Hero:hid_constructor_plasmadamage_easter_sr_t01" - Miss Bunny Penny
		"Hero:hid_constructor_plasmadamage_easter_sr_t02" - Miss Bunny Penny
		"Hero:hid_constructor_plasmadamage_easter_sr_t03" - Miss Bunny Penny
		"Hero:hid_constructor_plasmadamage_easter_sr_t04" - Miss Bunny Penny
		"Hero:hid_constructor_plasmadamage_easter_sr_t05" - Miss Bunny Penny
		"Hero:hid_constructor_plasmadamage_r_t01" - Plasma Specialist Izza"
		"Hero:hid_constructor_plasmadamage_r_t02" - Plasma Specialist Izza"
		"Hero:hid_constructor_plasmadamage_r_t03" - Plasma Specialist Izza"
		"Hero:hid_constructor_plasmadamage_r_t04" - Plasma Specialist Izza"
		"Hero:hid_constructor_plasmadamage_sr_t01" - Plasma Specialist Izza"
		"Hero:hid_constructor_plasmadamage_sr_t02" - Plasma Specialist Izza"
		"Hero:hid_constructor_plasmadamage_sr_t03" - Plasma Specialist Izza"
		"Hero:hid_constructor_plasmadamage_sr_t04" - Plasma Specialist Izza"
		"Hero:hid_constructor_plasmadamage_sr_t05" - Plasma Specialist Izza"
		"Hero:hid_constructor_plasmadamage_vr_t01" - Plasma Specialist Izza"
		"Hero:hid_constructor_plasmadamage_vr_t02" - Plasma Specialist Izza"
		"Hero:hid_constructor_plasmadamage_vr_t03" - Plasma Specialist Izza"
		"Hero:hid_constructor_plasmadamage_vr_t04" - Plasma Specialist Izza"
		"Hero:hid_constructor_plasmadamage_vr_t05" - Plasma Specialist Izza"
		"Hero:hid_constructor_rushbase_f_sr_t01" - Marathon Hype
		"Hero:hid_constructor_rushbase_f_sr_t02" - Marathon Hype
		"Hero:hid_constructor_rushbase_f_sr_t03" - Marathon Hype
		"Hero:hid_constructor_rushbase_f_sr_t04" - Marathon Hype
		"Hero:hid_constructor_rushbase_f_sr_t05" - Marathon Hype
		"Hero:hid_constructor_rushbase_f_vr_t01" - Marathon Hype
		"Hero:hid_constructor_rushbase_f_vr_t02" - Marathon Hype
		"Hero:hid_constructor_rushbase_f_vr_t03" - Marathon Hype
		"Hero:hid_constructor_rushbase_f_vr_t04" - Marathon Hype
		"Hero:hid_constructor_rushbase_f_vr_t05" - Marathon Hype
		"Hero:hid_constructor_rushbase_r_t01" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_r_t02" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_r_t03" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_r_t04" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_sr_t01" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_sr_t02" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_sr_t03" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_sr_t04" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_sr_t05" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_uc_t01" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_uc_t02" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_uc_t03" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_vr_t01" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_vr_t02" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_vr_t03" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_vr_t04" - B.A.S.E. Kyle
		"Hero:hid_constructor_rushbase_vr_t05" - B.A.S.E. Kyle
		"Hero:hid_constructor_sony_r_t01" - Guardian Penny
		"Hero:hid_constructor_sony_r_t02" - Guardian Penny
		"Hero:hid_constructor_sony_r_t03" - Guardian Penny
		"Hero:hid_constructor_sony_r_t04" - Guardian Penny
		"Hero:hid_constructor_sony_sr_t01" - Guardian Penny
		"Hero:hid_constructor_sony_sr_t02" - Guardian Penny
		"Hero:hid_constructor_sony_sr_t03" - Guardian Penny
		"Hero:hid_constructor_sony_sr_t04" - Guardian Penny
		"Hero:hid_constructor_sony_sr_t05" - Guardian Penny
		"Hero:hid_constructor_sony_vr_t01" - Guardian Penny
		"Hero:hid_constructor_sony_vr_t02" - Guardian Penny
		"Hero:hid_constructor_sony_vr_t03" - Guardian Penny
		"Hero:hid_constructor_sony_vr_t04" - Guardian Penny
		"Hero:hid_constructor_sony_vr_t05" - Guardian Penny
		"Hero:hid_constructor_xbox_r_t01" - Guardian Knox"
		"Hero:hid_constructor_xbox_r_t02" - Guardian Knox"
		"Hero:hid_constructor_xbox_r_t03" - Guardian Knox"
		"Hero:hid_constructor_xbox_r_t04" - Guardian Knox"
		"Hero:hid_constructor_xbox_sr_t01" - Guardian Knox"
		"Hero:hid_constructor_xbox_sr_t02" - Guardian Knox"
		"Hero:hid_constructor_xbox_sr_t03" - Guardian Knox"
		"Hero:hid_constructor_xbox_sr_t04" - Guardian Knox"
		"Hero:hid_constructor_xbox_sr_t05" - Guardian Knox"
		"Hero:hid_constructor_xbox_vr_t01" - Guardian Knox"
		"Hero:hid_constructor_xbox_vr_t02" - Guardian Knox"
		"Hero:hid_constructor_xbox_vr_t03" - Guardian Knox"
		"Hero:hid_constructor_xbox_vr_t04" - Guardian Knox"
		"Hero:hid_constructor_xbox_vr_t05" - Guardian Knox"







	NINJAS:
		"Hero:hid_ninja_007_r_t01" - Brawler Luna"
		"Hero:hid_ninja_007_r_t02" - Brawler Luna"
		"Hero:hid_ninja_007_r_t03" - Brawler Luna"
		"Hero:hid_ninja_007_r_t04" - Brawler Luna"
		"Hero:hid_ninja_007_sr_t01" - Brawler Luna"
		"Hero:hid_ninja_007_sr_t02" - Brawler Luna"
		"Hero:hid_ninja_007_sr_t03" - Brawler Luna"
		"Hero:hid_ninja_007_sr_t04" - Brawler Luna"
		"Hero:hid_ninja_007_sr_t05" - Brawler Luna"
		"Hero:hid_ninja_007_uc_t01" - Brawler Luna"
		"Hero:hid_ninja_007_uc_t02" - Brawler Luna"
		"Hero:hid_ninja_007_uc_t03" - Brawler Luna"
		"Hero:hid_ninja_007_vr_t01" - Brawler Luna"
		"Hero:hid_ninja_007_vr_t02" - Brawler Luna"
		"Hero:hid_ninja_007_vr_t03" - Brawler Luna"
		"Hero:hid_ninja_007_vr_t04" - Brawler Luna"
		"Hero:hid_ninja_007_vr_t05" - Brawler Luna"
		"Hero:hid_ninja_008_r_t01" - Stonefoot Crash"
		"Hero:hid_ninja_008_r_t02" - Stonefoot Crash"
		"Hero:hid_ninja_008_r_t03" - Stonefoot Crash"
		"Hero:hid_ninja_008_r_t04" - Stonefoot Crash"
		"Hero:hid_ninja_008_sr_t01" - Stonefoot Crash"
		"Hero:hid_ninja_008_sr_t02" - Stonefoot Crash"
		"Hero:hid_ninja_008_sr_t03" - Stonefoot Crash"
		"Hero:hid_ninja_008_sr_t04" - Stonefoot Crash"
		"Hero:hid_ninja_008_sr_t05" - Stonefoot Crash"
		"Hero:hid_ninja_008_vr_t01" - Stonefoot Crash"
		"Hero:hid_ninja_008_vr_t02" - Stonefoot Crash"
		"Hero:hid_ninja_008_vr_t03" - Stonefoot Crash"
		"Hero:hid_ninja_008_vr_t04" - Stonefoot Crash"
		"Hero:hid_ninja_008_vr_t05" - Stonefoot Crash"
		"Hero:hid_ninja_009_f_valentine_sr_t01" - Snuggle Specialist Sarah"
		"Hero:hid_ninja_009_f_valentine_sr_t02" - Snuggle Specialist Sarah"
		"Hero:hid_ninja_009_f_valentine_sr_t03" - Snuggle Specialist Sarah"
		"Hero:hid_ninja_009_f_valentine_sr_t04" - Snuggle Specialist Sarah"
		"Hero:hid_ninja_009_f_valentine_sr_t05" - Snuggle Specialist Sarah"
		"Hero:hid_ninja_009_r_t01" - Skirmisher Edge
		"Hero:hid_ninja_009_r_t02" - Skirmisher Edge
		"Hero:hid_ninja_009_r_t03" - Skirmisher Edge
		"Hero:hid_ninja_009_r_t04" - Skirmisher Edge
		"Hero:hid_ninja_009_sr_t01" - Skirmisher Edge
		"Hero:hid_ninja_009_sr_t02" - Skirmisher Edge
		"Hero:hid_ninja_009_sr_t03" - Skirmisher Edge
		"Hero:hid_ninja_009_sr_t04" - Skirmisher Edge
		"Hero:hid_ninja_009_sr_t05" - Skirmisher Edge
		"Hero:hid_ninja_009_vr_t01" - Skirmisher Edge
		"Hero:hid_ninja_009_vr_t02" - Skirmisher Edge
		"Hero:hid_ninja_009_vr_t03" - Skirmisher Edge
		"Hero:hid_ninja_009_vr_t04" - Skirmisher Edge
		"Hero:hid_ninja_009_vr_t05" - Skirmisher Edge
		"Hero:hid_ninja_010_f_sr_t01" - Deadly Blade Crash"
		"Hero:hid_ninja_010_f_sr_t02" - Deadly Blade Crash"
		"Hero:hid_ninja_010_f_sr_t03" - Deadly Blade Crash"
		"Hero:hid_ninja_010_f_sr_t04" - Deadly Blade Crash"
		"Hero:hid_ninja_010_f_sr_t05" - Deadly Blade Crash"
		"Hero:hid_ninja_010_f_vr_t01" - Deadly Blade Crash"
		"Hero:hid_ninja_010_f_vr_t02" - Deadly Blade Crash"
		"Hero:hid_ninja_010_f_vr_t03" - Deadly Blade Crash"
		"Hero:hid_ninja_010_f_vr_t04" - Deadly Blade Crash"
		"Hero:hid_ninja_010_f_vr_t05" - Deadly Blade Crash"
		"Hero:hid_ninja_010_sr_t01" - Deadly Star Scorpion"
		"Hero:hid_ninja_010_sr_t02" - Deadly Star Scorpion"
		"Hero:hid_ninja_010_sr_t03" - Deadly Star Scorpion"
		"Hero:hid_ninja_010_sr_t04" - Deadly Star Scorpion"
		"Hero:hid_ninja_010_sr_t05" - Deadly Star Scorpion"
		"Hero:hid_ninja_010_vr_t01" - Deadly Star Scorpion"
		"Hero:hid_ninja_010_vr_t02" - Deadly Star Scorpion"
		"Hero:hid_ninja_010_vr_t03" - Deadly Star Scorpion"
		"Hero:hid_ninja_010_vr_t04" - Deadly Star Scorpion"
		"Hero:hid_ninja_010_vr_t05" - Deadly Star Scorpion"
		"Hero:hid_ninja_011_r_t01" - Energy Thief Mari"
		"Hero:hid_ninja_011_r_t02" - Energy Thief Mari"
		"Hero:hid_ninja_011_r_t03" - Energy Thief Mari"
		"Hero:hid_ninja_011_r_t04" - Energy Thief Mari"
		"Hero:hid_ninja_011_sr_t01" - Energy Thief Mari"
		"Hero:hid_ninja_011_sr_t02" - Energy Thief Mari"
		"Hero:hid_ninja_011_sr_t03" - Energy Thief Mari"
		"Hero:hid_ninja_011_sr_t04" - Energy Thief Mari"
		"Hero:hid_ninja_011_sr_t05" - Energy Thief Mari"
		"Hero:hid_ninja_011_vr_t01" - Energy Thief Mari"
		"Hero:hid_ninja_011_vr_t02" - Energy Thief Mari"
		"Hero:hid_ninja_011_vr_t03" - Energy Thief Mari"
		"Hero:hid_ninja_011_vr_t04" - Energy Thief Mari"
		"Hero:hid_ninja_011_vr_t05" - Energy Thief Mari"
		"Hero:hid_ninja_013_r_t01" - Alchemist Sarah"
		"Hero:hid_ninja_013_r_t02" - Alchemist Sarah"
		"Hero:hid_ninja_013_r_t03" - Alchemist Sarah"
		"Hero:hid_ninja_013_r_t04" - Alchemist Sarah"
		"Hero:hid_ninja_013_sr_t01" - Alchemist Sarah"
		"Hero:hid_ninja_013_sr_t02" - Alchemist Sarah"
		"Hero:hid_ninja_013_sr_t03" - Alchemist Sarah"
		"Hero:hid_ninja_013_sr_t04" - Alchemist Sarah"
		"Hero:hid_ninja_013_sr_t05" - Alchemist Sarah"
		"Hero:hid_ninja_013_vr_t01" - Alchemist Sarah"
		"Hero:hid_ninja_013_vr_t02" - Alchemist Sarah"
		"Hero:hid_ninja_013_vr_t03" - Alchemist Sarah"
		"Hero:hid_ninja_013_vr_t04" - Alchemist Sarah"
		"Hero:hid_ninja_013_vr_t05" - Alchemist Sarah"
		"Hero:hid_ninja_014_f_sr_t01" - Thunderstrike Mari"
		"Hero:hid_ninja_014_f_sr_t02" - Thunderstrike Mari"
		"Hero:hid_ninja_014_f_sr_t03" - Thunderstrike Mari"
		"Hero:hid_ninja_014_f_sr_t04" - Thunderstrike Mari"
		"Hero:hid_ninja_014_f_sr_t05" - Thunderstrike Mari"
		"Hero:hid_ninja_014_r_t01" - Whirlwind Scorch"
		"Hero:hid_ninja_014_r_t02" - Whirlwind Scorch"
		"Hero:hid_ninja_014_r_t03" - Whirlwind Scorch"
		"Hero:hid_ninja_014_r_t04" - Whirlwind Scorch"
		"Hero:hid_ninja_014_sr_t01" - Whirlwind Scorch"
		"Hero:hid_ninja_014_sr_t02" - Whirlwind Scorch"
		"Hero:hid_ninja_014_sr_t03" - Whirlwind Scorch"
		"Hero:hid_ninja_014_sr_t04" - Whirlwind Scorch"
		"Hero:hid_ninja_014_sr_t05" - Whirlwind Scorch"
		"Hero:hid_ninja_014_uc_t01" - Whirlwind Scorch"
		"Hero:hid_ninja_014_uc_t02" - Whirlwind Scorch"
		"Hero:hid_ninja_014_uc_t03" - Whirlwind Scorch"
		"Hero:hid_ninja_014_vr_t01" - Whirlwind Scorch"
		"Hero:hid_ninja_014_vr_t02" - Whirlwind Scorch"
		"Hero:hid_ninja_014_vr_t03" - Whirlwind Scorch"
		"Hero:hid_ninja_014_vr_t04" - Whirlwind Scorch"
		"Hero:hid_ninja_014_vr_t05" - Whirlwind Scorch"
		"Hero:hid_ninja_015_f_v1_r_t01" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_r_t02" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_r_t03" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_r_t04" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_roadtrip_sr_t01" - Whiteout Fiona"
		"Hero:hid_ninja_015_f_v1_roadtrip_sr_t02" - Whiteout Fiona"
		"Hero:hid_ninja_015_f_v1_roadtrip_sr_t03" - Whiteout Fiona"
		"Hero:hid_ninja_015_f_v1_roadtrip_sr_t04" - Whiteout Fiona"
		"Hero:hid_ninja_015_f_v1_roadtrip_sr_t05" - Whiteout Fiona"
		"Hero:hid_ninja_015_f_v1_sr_t01" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_sr_t02" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_sr_t03" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_sr_t04" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_sr_t05" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_uc_t01" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_uc_t02" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_uc_t03" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_vr_t01" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_vr_t02" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_vr_t03" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_vr_t04" - Harvester Sarah"
		"Hero:hid_ninja_015_f_v1_vr_t05" - Harvester Sarah"
		"Hero:hid_ninja_016_f_v1_sr_t01" - Deadly Lotus Luna"
		"Hero:hid_ninja_016_f_v1_sr_t02" - Deadly Lotus Luna"
		"Hero:hid_ninja_016_f_v1_sr_t03" - Deadly Lotus Luna"
		"Hero:hid_ninja_016_f_v1_sr_t04" - Deadly Lotus Luna"
		"Hero:hid_ninja_016_f_v1_sr_t05" - Deadly Lotus Luna"
		"Hero:hid_ninja_016_m_v1_sr_t01" - Piercing Lotus Edge
		"Hero:hid_ninja_016_m_v1_sr_t02" - Piercing Lotus Edge
		"Hero:hid_ninja_016_m_v1_sr_t03" - Piercing Lotus Edge
		"Hero:hid_ninja_016_m_v1_sr_t04" - Piercing Lotus Edge
		"Hero:hid_ninja_016_m_v1_sr_t05" - Piercing Lotus Edge
		"Hero:hid_ninja_016_m_v1_vr_t01" - Piercing Lotus Edge
		"Hero:hid_ninja_016_m_v1_vr_t02" - Piercing Lotus Edge
		"Hero:hid_ninja_016_m_v1_vr_t03" - Piercing Lotus Edge
		"Hero:hid_ninja_016_m_v1_vr_t04" - Piercing Lotus Edge
		"Hero:hid_ninja_016_m_v1_vr_t05" - Piercing Lotus Edge
		"Hero:hid_ninja_017_m_v1_r_t01" - Infiltrator Ken"
		"Hero:hid_ninja_017_m_v1_r_t02" - Infiltrator Ken"
		"Hero:hid_ninja_017_m_v1_r_t03" - Infiltrator Ken"
		"Hero:hid_ninja_017_m_v1_r_t04" - Infiltrator Ken"
		"Hero:hid_ninja_017_m_v1_sr_t01" - Infiltrator Ken"
		"Hero:hid_ninja_017_m_v1_sr_t02" - Infiltrator Ken"
		"Hero:hid_ninja_017_m_v1_sr_t03" - Infiltrator Ken"
		"Hero:hid_ninja_017_m_v1_sr_t04" - Infiltrator Ken"
		"Hero:hid_ninja_017_m_v1_sr_t05" - Infiltrator Ken"
		"Hero:hid_ninja_017_m_v1_vr_t01" - Infiltrator Ken"
		"Hero:hid_ninja_017_m_v1_vr_t02" - Infiltrator Ken"
		"Hero:hid_ninja_017_m_v1_vr_t03" - Infiltrator Ken"
		"Hero:hid_ninja_017_m_v1_vr_t04" - Infiltrator Ken"
		"Hero:hid_ninja_017_m_v1_vr_t05" - Infiltrator Ken"
		"Hero:hid_ninja_018_sr_t01" - Plague Doctor Igor
		"Hero:hid_ninja_018_sr_t02" - Plague Doctor Igor
		"Hero:hid_ninja_018_sr_t03" - Plague Doctor Igor
		"Hero:hid_ninja_018_sr_t04" - Plague Doctor Igor
		"Hero:hid_ninja_018_sr_t05" - Plague Doctor Igor
		"Hero:hid_ninja_019_sr_t01" - Dire
		"Hero:hid_ninja_019_sr_t02" - Dire
		"Hero:hid_ninja_019_sr_t03" - Dire
		"Hero:hid_ninja_019_sr_t04" - Dire
		"Hero:hid_ninja_019_sr_t05" - Dire
		"Hero:hid_ninja_020_sr_t01" - Cloaked Shadow"
		"Hero:hid_ninja_020_sr_t02" - Cloaked Shadow"
		"Hero:hid_ninja_020_sr_t03" - Cloaked Shadow"
		"Hero:hid_ninja_020_sr_t04" - Cloaked Shadow"
		"Hero:hid_ninja_020_sr_t05" - Cloaked Shadow"
		"Hero:hid_ninja_021_sr_t01" - Forged Fate
		"Hero:hid_ninja_021_sr_t02" - Forged Fate
		"Hero:hid_ninja_021_sr_t03" - Forged Fate
		"Hero:hid_ninja_021_sr_t04" - Forged Fate
		"Hero:hid_ninja_021_sr_t05" - Forged Fate
		"Hero:hid_ninja_022_sr_t01" - Overtaker Hiro"
		"Hero:hid_ninja_022_sr_t02" - Overtaker Hiro"
		"Hero:hid_ninja_022_sr_t03" - Overtaker Hiro"
		"Hero:hid_ninja_022_sr_t04" - Overtaker Hiro"
		"Hero:hid_ninja_022_sr_t05" - Overtaker Hiro"
		"Hero:hid_ninja_023_sr_t01" - Lynx Kassandra"
		"Hero:hid_ninja_023_sr_t02" - Lynx Kassandra"
		"Hero:hid_ninja_023_sr_t03" - Lynx Kassandra"
		"Hero:hid_ninja_023_sr_t04" - Lynx Kassandra"
		"Hero:hid_ninja_023_sr_t05" - Lynx Kassandra"
		"Hero:hid_ninja_024_sr_t01" - Anti-Cuddle Sarah"
		"Hero:hid_ninja_024_sr_t02" - Anti-Cuddle Sarah"
		"Hero:hid_ninja_024_sr_t03" - Anti-Cuddle Sarah"
		"Hero:hid_ninja_024_sr_t04" - Anti-Cuddle Sarah"
		"Hero:hid_ninja_024_sr_t05" - Anti-Cuddle Sarah"
		"Hero:hid_ninja_025_pirateninja_sr_t01" - Swashbuckler Keelhaul"
		"Hero:hid_ninja_025_pirateninja_sr_t02" - Swashbuckler Keelhaul"
		"Hero:hid_ninja_025_pirateninja_sr_t03" - Swashbuckler Keelhaul"
		"Hero:hid_ninja_025_pirateninja_sr_t04" - Swashbuckler Keelhaul"
		"Hero:hid_ninja_025_pirateninja_sr_t05" - Swashbuckler Keelhaul"
		"Hero:hid_ninja_025_pirateninja_vr_t01" - Swashbuckler Keelhaul"
		"Hero:hid_ninja_025_pirateninja_vr_t02" - Swashbuckler Keelhaul"
		"Hero:hid_ninja_025_pirateninja_vr_t03" - Swashbuckler Keelhaul"
		"Hero:hid_ninja_025_pirateninja_vr_t04" - Swashbuckler Keelhaul"
		"Hero:hid_ninja_025_pirateninja_vr_t05" - Swashbuckler Keelhaul"
		"Hero:hid_ninja_026_reddragonninja_sr_t01" - Hybrid"
		"Hero:hid_ninja_026_reddragonninja_sr_t02" - Hybrid"
		"Hero:hid_ninja_026_reddragonninja_sr_t03" - Hybrid"
		"Hero:hid_ninja_026_reddragonninja_sr_t04" - Hybrid"
		"Hero:hid_ninja_026_reddragonninja_sr_t05" - Hybrid"
		"Hero:hid_ninja_027_bunnyninja_sr_t01" - Dashing Hare Ken"
		"Hero:hid_ninja_027_bunnyninja_sr_t02" - Dashing Hare Ken"
		"Hero:hid_ninja_027_bunnyninja_sr_t03" - Dashing Hare Ken"
		"Hero:hid_ninja_027_bunnyninja_sr_t04" - Dashing Hare Ken"
		"Hero:hid_ninja_027_bunnyninja_sr_t05" - Dashing Hare Ken"
		"Hero:hid_ninja_028_razor_sr_t01" - Razor
		"Hero:hid_ninja_028_razor_sr_t02" - Razor
		"Hero:hid_ninja_028_razor_sr_t03" - Razor
		"Hero:hid_ninja_028_razor_sr_t04" - Razor
		"Hero:hid_ninja_028_razor_sr_t05" - Razor
		"Hero:hid_ninja_029_dinoninja_sr_t01" - Paleo Luna"
		"Hero:hid_ninja_029_dinoninja_sr_t02" - Paleo Luna"
		"Hero:hid_ninja_029_dinoninja_sr_t03" - Paleo Luna"
		"Hero:hid_ninja_029_dinoninja_sr_t04" - Paleo Luna"
		"Hero:hid_ninja_029_dinoninja_sr_t05" - Paleo Luna"
		"Hero:hid_ninja_030_retroscifininja_sr_t01" - Intergalactic Ken"
		"Hero:hid_ninja_030_retroscifininja_sr_t02" - Intergalactic Ken"
		"Hero:hid_ninja_030_retroscifininja_sr_t03" - Intergalactic Ken"
		"Hero:hid_ninja_030_retroscifininja_sr_t04" - Intergalactic Ken"
		"Hero:hid_ninja_030_retroscifininja_sr_t05" - Intergalactic Ken"
		"Hero:hid_ninja_030_retroscifininja_vr_t01" - Intergalactic Ken"
		"Hero:hid_ninja_030_retroscifininja_vr_t02" - Intergalactic Ken"
		"Hero:hid_ninja_030_retroscifininja_vr_t03" - Intergalactic Ken"
		"Hero:hid_ninja_030_retroscifininja_vr_t04" - Intergalactic Ken"
		"Hero:hid_ninja_030_retroscifininja_vr_t05" - Intergalactic Ken"
		"Hero:hid_ninja_031_radninja_sr_t01" - Varsity Hiro"
		"Hero:hid_ninja_031_radninja_sr_t02" - Varsity Hiro"
		"Hero:hid_ninja_031_radninja_sr_t03" - Varsity Hiro"
		"Hero:hid_ninja_031_radninja_sr_t04" - Varsity Hiro"
		"Hero:hid_ninja_031_radninja_sr_t05" - Varsity Hiro"
		"Hero:hid_ninja_031_radninja_vr_t01" - Varsity Hiro"
		"Hero:hid_ninja_031_radninja_vr_t02" - Varsity Hiro"
		"Hero:hid_ninja_031_radninja_vr_t03" - Varsity Hiro"
		"Hero:hid_ninja_031_radninja_vr_t04" - Varsity Hiro"
		"Hero:hid_ninja_031_radninja_vr_t05" - Varsity Hiro"
		"Hero:hid_ninja_033_halloweenninja_sr_t01" - Mermonster Ken"
		"Hero:hid_ninja_033_halloweenninja_sr_t02" - Mermonster Ken"
		"Hero:hid_ninja_033_halloweenninja_sr_t03" - Mermonster Ken"
		"Hero:hid_ninja_033_halloweenninja_sr_t04" - Mermonster Ken"
		"Hero:hid_ninja_033_halloweenninja_sr_t05" - Mermonster Ken"
		"Hero:hid_ninja_034_toymonkey_sr_t01" - Monks"
		"Hero:hid_ninja_034_toymonkey_sr_t02" - Monks"
		"Hero:hid_ninja_034_toymonkey_sr_t03" - Monks"
		"Hero:hid_ninja_034_toymonkey_sr_t04" - Monks"
		"Hero:hid_ninja_034_toymonkey_sr_t05" - Monks"
		"Hero:hid_ninja_034_toymonkey_vr_t01" - Monks"
		"Hero:hid_ninja_034_toymonkey_vr_t02" - Monks"
		"Hero:hid_ninja_034_toymonkey_vr_t03" - Monks"
		"Hero:hid_ninja_034_toymonkey_vr_t04" - Monks"
		"Hero:hid_ninja_034_toymonkey_vr_t05" - Monks"
		"Hero:hid_ninja_035_f_cupid_sr_t01" - Stoneheart Farrah"
		"Hero:hid_ninja_035_f_cupid_sr_t02" - Stoneheart Farrah"
		"Hero:hid_ninja_035_f_cupid_sr_t03" - Stoneheart Farrah"
		"Hero:hid_ninja_035_f_cupid_sr_t04" - Stoneheart Farrah"
		"Hero:hid_ninja_035_f_cupid_sr_t05" - Stoneheart Farrah"
		"Hero:hid_ninja_037_junk_samurai_sr_t01" - Samurai Scrapper
		"Hero:hid_ninja_037_junk_samurai_sr_t02" - Samurai Scrapper
		"Hero:hid_ninja_037_junk_samurai_sr_t03" - Samurai Scrapper
		"Hero:hid_ninja_037_junk_samurai_sr_t04" - Samurai Scrapper
		"Hero:hid_ninja_037_junk_samurai_sr_t05" - Samurai Scrapper
		"Hero:hid_ninja_037_junk_samurai_vr_t01" - Samurai Scrapper
		"Hero:hid_ninja_037_junk_samurai_vr_t02" - Samurai Scrapper
		"Hero:hid_ninja_037_junk_samurai_vr_t03" - Samurai Scrapper
		"Hero:hid_ninja_037_junk_samurai_vr_t04" - Samurai Scrapper
		"Hero:hid_ninja_037_junk_samurai_vr_t05" - Samurai Scrapper
		"Hero:hid_ninja_038_male_ninja_pirate_sr_t01" - Freebooter Ken"
		"Hero:hid_ninja_038_male_ninja_pirate_sr_t02" - Freebooter Ken"
		"Hero:hid_ninja_038_male_ninja_pirate_sr_t03" - Freebooter Ken"
		"Hero:hid_ninja_038_male_ninja_pirate_sr_t04" - Freebooter Ken"
		"Hero:hid_ninja_038_male_ninja_pirate_sr_t05" - Freebooter Ken"
		"Hero:hid_ninja_038_male_ninja_pirate_vr_t01" - Freebooter Ken"
		"Hero:hid_ninja_038_male_ninja_pirate_vr_t02" - Freebooter Ken"
		"Hero:hid_ninja_038_male_ninja_pirate_vr_t03" - Freebooter Ken"
		"Hero:hid_ninja_038_male_ninja_pirate_vr_t04" - Freebooter Ken"
		"Hero:hid_ninja_038_male_ninja_pirate_vr_t05" - Freebooter Ken"
		"Hero:hid_ninja_039_dino_ninja_sr_t01" - Jurassic Ken"
		"Hero:hid_ninja_039_dino_ninja_sr_t02" - Jurassic Ken"
		"Hero:hid_ninja_039_dino_ninja_sr_t03" - Jurassic Ken"
		"Hero:hid_ninja_039_dino_ninja_sr_t04" - Jurassic Ken"
		"Hero:hid_ninja_039_dino_ninja_sr_t05" - Jurassic Ken"
		"Hero:hid_ninja_039_dino_ninja_vr_t01" - Jurassic Ken"
		"Hero:hid_ninja_039_dino_ninja_vr_t02" - Jurassic Ken"
		"Hero:hid_ninja_039_dino_ninja_vr_t03" - Jurassic Ken"
		"Hero:hid_ninja_039_dino_ninja_vr_t04" - Jurassic Ken"
		"Hero:hid_ninja_039_dino_ninja_vr_t05" - Jurassic Ken"
		"Hero:hid_ninja_040_dennis_sr_t01" - Dennis"
		"Hero:hid_ninja_040_dennis_sr_t02" - Dennis"
		"Hero:hid_ninja_040_dennis_sr_t03" - Dennis"
		"Hero:hid_ninja_040_dennis_sr_t04" - Dennis"
		"Hero:hid_ninja_040_dennis_sr_t05" - Dennis"
		"Hero:hid_ninja_040_dennis_vr_t01" - Dennis"
		"Hero:hid_ninja_040_dennis_vr_t02" - Dennis"
		"Hero:hid_ninja_040_dennis_vr_t03" - Dennis"
		"Hero:hid_ninja_040_dennis_vr_t04" - Dennis"
		"Hero:hid_ninja_040_dennis_vr_t05" - Dennis"
		"Hero:hid_ninja_041_deco_sr_t01" - Venturion"
		"Hero:hid_ninja_041_deco_sr_t02" - Venturion"
		"Hero:hid_ninja_041_deco_sr_t03" - Venturion"
		"Hero:hid_ninja_041_deco_sr_t04" - Venturion"
		"Hero:hid_ninja_041_deco_sr_t05" - Venturion"
		"Hero:hid_ninja_041_deco_vr_t01" - Venturion"
		"Hero:hid_ninja_041_deco_vr_t02" - Venturion"
		"Hero:hid_ninja_041_deco_vr_t03" - Venturion"
		"Hero:hid_ninja_041_deco_vr_t04" - Venturion"
		"Hero:hid_ninja_041_deco_vr_t05" - Venturion"
		"Hero:hid_ninja_myth02_sr_t01" - The Cloaked Star
		"Hero:hid_ninja_myth02_sr_t02" - The Cloaked Star
		"Hero:hid_ninja_myth02_sr_t03" - The Cloaked Star
		"Hero:hid_ninja_myth02_sr_t04" - The Cloaked Star
		"Hero:hid_ninja_myth02_sr_t05" - The Cloaked Star
		"Hero:hid_ninja_myth03_sr_t01" - Bladestorm Enforcer
		"Hero:hid_ninja_myth03_sr_t02" - Bladestorm Enforcer
		"Hero:hid_ninja_myth03_sr_t03" - Bladestorm Enforcer
		"Hero:hid_ninja_myth03_sr_t04" - Bladestorm Enforcer
		"Hero:hid_ninja_myth03_sr_t05" - Bladestorm Enforcer
		"Hero:hid_ninja_slashbreath_r_t01" - Dragon Scorch"
		"Hero:hid_ninja_slashbreath_r_t02" - Dragon Scorch"
		"Hero:hid_ninja_slashbreath_r_t03" - Dragon Scorch"
		"Hero:hid_ninja_slashbreath_r_t04" - Dragon Scorch"
		"Hero:hid_ninja_slashbreath_sr_t01" - Dragon Scorch"
		"Hero:hid_ninja_slashbreath_sr_t02" - Dragon Scorch"
		"Hero:hid_ninja_slashbreath_sr_t03" - Dragon Scorch"
		"Hero:hid_ninja_slashbreath_sr_t04" - Dragon Scorch"
		"Hero:hid_ninja_slashbreath_sr_t05" - Dragon Scorch"
		"Hero:hid_ninja_slashbreath_vr_t01" - Dragon Scorch"
		"Hero:hid_ninja_slashbreath_vr_t02" - Dragon Scorch"
		"Hero:hid_ninja_slashbreath_vr_t03" - Dragon Scorch"
		"Hero:hid_ninja_slashbreath_vr_t04" - Dragon Scorch"
		"Hero:hid_ninja_slashbreath_vr_t05" - Dragon Scorch"
		"Hero:hid_ninja_slashbreathhw_sr_t01" - Sarah Hotep"
		"Hero:hid_ninja_slashbreathhw_sr_t02" - Sarah Hotep"
		"Hero:hid_ninja_slashbreathhw_sr_t03" - Sarah Hotep"
		"Hero:hid_ninja_slashbreathhw_sr_t04" - Sarah Hotep"
		"Hero:hid_ninja_slashbreathhw_sr_t05" - Sarah Hotep"
		"Hero:hid_ninja_slashbreathhw_vr_t01" - Sarah Hotep"
		"Hero:hid_ninja_slashbreathhw_vr_t02" - Sarah Hotep"
		"Hero:hid_ninja_slashbreathhw_vr_t03" - Sarah Hotep"
		"Hero:hid_ninja_slashbreathhw_vr_t04" - Sarah Hotep"
		"Hero:hid_ninja_slashbreathhw_vr_t05" - Sarah Hotep"
		"Hero:hid_ninja_slashtail_r_t01" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_r_t02" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_r_t03" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_r_t04" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_sr_t01" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_sr_t02" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_sr_t03" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_sr_t04" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_sr_t05" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_uc_t01" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_uc_t02" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_uc_t03" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_vr_t01" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_vr_t02" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_vr_t03" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_vr_t04" - Fleetfoot Ken"
		"Hero:hid_ninja_slashtail_vr_t05" - Fleetfoot Ken"
		"Hero:hid_ninja_smokedimmak_r_t01" - Dim Mak Mari"
		"Hero:hid_ninja_smokedimmak_r_t02" - Dim Mak Mari"
		"Hero:hid_ninja_smokedimmak_r_t03" - Dim Mak Mari"
		"Hero:hid_ninja_smokedimmak_r_t04" - Dim Mak Mari"
		"Hero:hid_ninja_smokedimmak_sr_t01" - Dim Mak Mari"
		"Hero:hid_ninja_smokedimmak_sr_t02" - Dim Mak Mari"
		"Hero:hid_ninja_smokedimmak_sr_t03" - Dim Mak Mari"
		"Hero:hid_ninja_smokedimmak_sr_t04" - Dim Mak Mari"
		"Hero:hid_ninja_smokedimmak_sr_t05" - Dim Mak Mari"
		"Hero:hid_ninja_smokedimmak_vr_t01" - Dim Mak Mari"
		"Hero:hid_ninja_smokedimmak_vr_t02" - Dim Mak Mari"
		"Hero:hid_ninja_smokedimmak_vr_t03" - Dim Mak Mari"
		"Hero:hid_ninja_smokedimmak_vr_t04" - Dim Mak Mari"
		"Hero:hid_ninja_smokedimmak_vr_t05" - Dim Mak Mari"
		"Hero:hid_ninja_sony_r_t01" - Bluestreak Ken"
		"Hero:hid_ninja_sony_r_t02" - Bluestreak Ken"
		"Hero:hid_ninja_sony_r_t03" - Bluestreak Ken"
		"Hero:hid_ninja_sony_r_t04" - Bluestreak Ken"
		"Hero:hid_ninja_sony_sr_t01" - Bluestreak Ken"
		"Hero:hid_ninja_sony_sr_t02" - Bluestreak Ken"
		"Hero:hid_ninja_sony_sr_t03" - Bluestreak Ken"
		"Hero:hid_ninja_sony_sr_t04" - Bluestreak Ken"
		"Hero:hid_ninja_sony_sr_t05" - Bluestreak Ken"
		"Hero:hid_ninja_sony_vr_t01" - Bluestreak Ken"
		"Hero:hid_ninja_sony_vr_t02" - Bluestreak Ken"
		"Hero:hid_ninja_sony_vr_t03" - Bluestreak Ken"
		"Hero:hid_ninja_sony_vr_t04" - Bluestreak Ken"
		"Hero:hid_ninja_sony_vr_t05" - Bluestreak Ken"
		"Hero:hid_ninja_starsassassin_foundersf_sr_t01" - Lotus Assassin Sarah"
		"Hero:hid_ninja_starsassassin_foundersf_sr_t02" - Lotus Assassin Sarah"
		"Hero:hid_ninja_starsassassin_foundersf_sr_t03" - Lotus Assassin Sarah"
		"Hero:hid_ninja_starsassassin_foundersf_sr_t04" - Lotus Assassin Sarah"
		"Hero:hid_ninja_starsassassin_foundersf_sr_t05" - Lotus Assassin Sarah"
		"Hero:hid_ninja_starsassassin_foundersm_sr_t01" - Lotus Assassin Ken"
		"Hero:hid_ninja_starsassassin_foundersm_sr_t02" - Lotus Assassin Ken"
		"Hero:hid_ninja_starsassassin_foundersm_sr_t03" - Lotus Assassin Ken"
		"Hero:hid_ninja_starsassassin_foundersm_sr_t04" - Lotus Assassin Ken"
		"Hero:hid_ninja_starsassassin_foundersm_sr_t05" - Lotus Assassin Ken"
		"Hero:hid_ninja_starsassassin_r_t01" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_r_t02" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_r_t03" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_r_t04" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_sr_t01" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_sr_t02" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_sr_t03" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_sr_t04" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_sr_t05" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_uc_t01" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_uc_t02" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_uc_t03" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_vr_t01" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_vr_t02" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_vr_t03" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_vr_t04" - Assassin Sarah"
		"Hero:hid_ninja_starsassassin_vr_t05" - Assassin Sarah"
		"Hero:hid_ninja_starsrain_sr_t01" - Shuriken Master Sarah"
		"Hero:hid_ninja_starsrain_sr_t02" - Shuriken Master Sarah"
		"Hero:hid_ninja_starsrain_sr_t03" - Shuriken Master Sarah"
		"Hero:hid_ninja_starsrain_sr_t04" - Shuriken Master Sarah"
		"Hero:hid_ninja_starsrain_sr_t05" - Shuriken Master Sarah"
		"Hero:hid_ninja_starsrain_vr_t01" - Shuriken Master Sarah"
		"Hero:hid_ninja_starsrain_vr_t02" - Shuriken Master Sarah"
		"Hero:hid_ninja_starsrain_vr_t03" - Shuriken Master Sarah"
		"Hero:hid_ninja_starsrain_vr_t04" - Shuriken Master Sarah"
		"Hero:hid_ninja_starsrain_vr_t05" - Shuriken Master Sarah"
		"Hero:hid_ninja_starsrainhw_sr_t01" - Swift Shuriken Llamurai"
		"Hero:hid_ninja_starsrainhw_sr_t02" - Swift Shuriken Llamurai"
		"Hero:hid_ninja_starsrainhw_sr_t03" - Swift Shuriken Llamurai"
		"Hero:hid_ninja_starsrainhw_sr_t04" - Swift Shuriken Llamurai"
		"Hero:hid_ninja_starsrainhw_sr_t05" - Swift Shuriken Llamurai"
		"Hero:hid_ninja_starsrainhw_vr_t01" - Swift Shuriken Llamurai"
		"Hero:hid_ninja_starsrainhw_vr_t02" - Swift Shuriken Llamurai"
		"Hero:hid_ninja_starsrainhw_vr_t03" - Swift Shuriken Llamurai"
		"Hero:hid_ninja_starsrainhw_vr_t04" - Swift Shuriken Llamurai"
		"Hero:hid_ninja_starsrainhw_vr_t05" - Swift Shuriken Llamurai"
		"Hero:hid_ninja_swordmaster_sr_t01" - Swordmaster Ken"
		"Hero:hid_ninja_swordmaster_sr_t02" - Swordmaster Ken"
		"Hero:hid_ninja_swordmaster_sr_t03" - Swordmaster Ken"
		"Hero:hid_ninja_swordmaster_sr_t04" - Swordmaster Ken"
		"Hero:hid_ninja_swordmaster_sr_t05" - Swordmaster Ken"
		"Hero:hid_ninja_test - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_r_t01" - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_r_t02" - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_r_t03" - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_r_t04" - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_sr_t01" - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_sr_t02" - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_sr_t03" - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_sr_t04" - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_sr_t05" - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_vr_t01" - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_vr_t02" - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_vr_t03" - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_vr_t04" - Jade Assassin Sarah"
		"Hero:hid_ninja_xbox_vr_t05" - Jade Assassin Sarah"












	OUTLANDERS:
		"Hero:hid_outlander_007_r_t01" - Enforcer Grizzly
		"Hero:hid_outlander_007_r_t02" - Enforcer Grizzly
		"Hero:hid_outlander_007_r_t03" - Enforcer Grizzly
		"Hero:hid_outlander_007_r_t04" - Enforcer Grizzly
		"Hero:hid_outlander_007_rs01_sr_t01" - Jingle Jess"
		"Hero:hid_outlander_007_rs01_sr_t02" - Jingle Jess"
		"Hero:hid_outlander_007_rs01_sr_t03" - Jingle Jess"
		"Hero:hid_outlander_007_rs01_sr_t04" - Jingle Jess"
		"Hero:hid_outlander_007_rs01_sr_t05" - Jingle Jess"
		"Hero:hid_outlander_007_sr_t01" - Enforcer Grizzly
		"Hero:hid_outlander_007_sr_t02" - Enforcer Grizzly
		"Hero:hid_outlander_007_sr_t03" - Enforcer Grizzly
		"Hero:hid_outlander_007_sr_t04" - Enforcer Grizzly
		"Hero:hid_outlander_007_sr_t05" - Enforcer Grizzly
		"Hero:hid_outlander_007_uc_t01" - Enforcer Grizzly
		"Hero:hid_outlander_007_uc_t02" - Enforcer Grizzly
		"Hero:hid_outlander_007_uc_t03" - Enforcer Grizzly
		"Hero:hid_outlander_007_vr_t01" - Enforcer Grizzly
		"Hero:hid_outlander_007_vr_t02" - Enforcer Grizzly
		"Hero:hid_outlander_007_vr_t03" - Enforcer Grizzly
		"Hero:hid_outlander_007_vr_t04" - Enforcer Grizzly
		"Hero:hid_outlander_007_vr_t05" - Enforcer Grizzly
		"Hero:hid_outlander_008_foundersf_sr_t01" - Recon Scout Jess"
		"Hero:hid_outlander_008_foundersf_sr_t02" - Recon Scout Jess"
		"Hero:hid_outlander_008_foundersf_sr_t03" - Recon Scout Jess"
		"Hero:hid_outlander_008_foundersf_sr_t04" - Recon Scout Jess"
		"Hero:hid_outlander_008_foundersf_sr_t05" - Recon Scout Jess"
		"Hero:hid_outlander_008_foundersm_sr_t01" - Recon Scout A.C."
		"Hero:hid_outlander_008_foundersm_sr_t02" - Recon Scout A.C."
		"Hero:hid_outlander_008_foundersm_sr_t03" - Recon Scout A.C."
		"Hero:hid_outlander_008_foundersm_sr_t04" - Recon Scout A.C."
		"Hero:hid_outlander_008_foundersm_sr_t05" - Recon Scout A.C."
		"Hero:hid_outlander_008_r_t01" - Recon Scout Eagle Eye
		"Hero:hid_outlander_008_r_t02" - Recon Scout Eagle Eye
		"Hero:hid_outlander_008_r_t03" - Recon Scout Eagle Eye
		"Hero:hid_outlander_008_r_t04" - Recon Scout Eagle Eye
		"Hero:hid_outlander_008_sr_t01" - Recon Scout Eagle Eye
		"Hero:hid_outlander_008_sr_t02" - Recon Scout Eagle Eye
		"Hero:hid_outlander_008_sr_t03" - Recon Scout Eagle Eye
		"Hero:hid_outlander_008_sr_t04" - Recon Scout Eagle Eye
		"Hero:hid_outlander_008_sr_t05" - Recon Scout Eagle Eye
		"Hero:hid_outlander_008_vr_t01" - Recon Scout Eagle Eye
		"Hero:hid_outlander_008_vr_t02" - Recon Scout Eagle Eye
		"Hero:hid_outlander_008_vr_t03" - Recon Scout Eagle Eye
		"Hero:hid_outlander_008_vr_t04" - Recon Scout Eagle Eye
		"Hero:hid_outlander_008_vr_t05" - Recon Scout Eagle Eye
		"Hero:hid_outlander_009_r_t01" - Vanguard Southie
		"Hero:hid_outlander_009_r_t02" - Vanguard Southie
		"Hero:hid_outlander_009_r_t03" - Vanguard Southie
		"Hero:hid_outlander_009_r_t04" - Vanguard Southie
		"Hero:hid_outlander_009_sr_t01" - Vanguard Southie
		"Hero:hid_outlander_009_sr_t02" - Vanguard Southie
		"Hero:hid_outlander_009_sr_t03" - Vanguard Southie
		"Hero:hid_outlander_009_sr_t04" - Vanguard Southie
		"Hero:hid_outlander_009_sr_t05" - Vanguard Southie
		"Hero:hid_outlander_009_vr_t01" - Vanguard Southie
		"Hero:hid_outlander_009_vr_t02" - Vanguard Southie
		"Hero:hid_outlander_009_vr_t03" - Vanguard Southie
		"Hero:hid_outlander_009_vr_t04" - Vanguard Southie
		"Hero:hid_outlander_009_vr_t05" - Vanguard Southie
		"Hero:hid_outlander_010_m_4thjuly_sr_t01" - Old Glory A.C."
		"Hero:hid_outlander_010_m_4thjuly_sr_t02" - Old Glory A.C."
		"Hero:hid_outlander_010_m_4thjuly_sr_t03" - Old Glory A.C."
		"Hero:hid_outlander_010_m_4thjuly_sr_t04" - Old Glory A.C."
		"Hero:hid_outlander_010_m_4thjuly_sr_t05" - Old Glory A.C."
		"Hero:hid_outlander_010_m_sr_t01" - Trailblaster A.C."
		"Hero:hid_outlander_010_m_sr_t02" - Trailblaster A.C."
		"Hero:hid_outlander_010_m_sr_t03" - Trailblaster A.C."
		"Hero:hid_outlander_010_m_sr_t04" - Trailblaster A.C."
		"Hero:hid_outlander_010_m_sr_t05" - Trailblaster A.C."
		"Hero:hid_outlander_010_m_vr_t01" - Trailblaster A.C."
		"Hero:hid_outlander_010_m_vr_t02" - Trailblaster A.C."
		"Hero:hid_outlander_010_m_vr_t03" - Trailblaster A.C."
		"Hero:hid_outlander_010_m_vr_t04" - Trailblaster A.C."
		"Hero:hid_outlander_010_m_vr_t05" - Trailblaster A.C."
		"Hero:hid_outlander_010_sr_t01" - Shockblaster Buzz
		"Hero:hid_outlander_010_sr_t02" - Shockblaster Buzz
		"Hero:hid_outlander_010_sr_t03" - Shockblaster Buzz
		"Hero:hid_outlander_010_sr_t04" - Shockblaster Buzz
		"Hero:hid_outlander_010_sr_t05" - Shockblaster Buzz
		"Hero:hid_outlander_010_vr_t01" - Shockblaster Buzz
		"Hero:hid_outlander_010_vr_t02" - Shockblaster Buzz
		"Hero:hid_outlander_010_vr_t03" - Shockblaster Buzz
		"Hero:hid_outlander_010_vr_t04" - Shockblaster Buzz
		"Hero:hid_outlander_010_vr_t05" - Shockblaster Buzz
		"Hero:hid_outlander_011_sr_t01" - Gunblazer Southie
		"Hero:hid_outlander_011_sr_t02" - Gunblazer Southie
		"Hero:hid_outlander_011_sr_t03" - Gunblazer Southie
		"Hero:hid_outlander_011_sr_t04" - Gunblazer Southie
		"Hero:hid_outlander_011_sr_t05" - Gunblazer Southie
		"Hero:hid_outlander_011_vr_t01" - Gunblazer Southie
		"Hero:hid_outlander_011_vr_t02" - Gunblazer Southie
		"Hero:hid_outlander_011_vr_t03" - Gunblazer Southie
		"Hero:hid_outlander_011_vr_t04" - Gunblazer Southie
		"Hero:hid_outlander_011_vr_t05" - Gunblazer Southie
		"Hero:hid_outlander_013_sr_t01" - Fragment Flurry Jess"
		"Hero:hid_outlander_013_sr_t02" - Fragment Flurry Jess"
		"Hero:hid_outlander_013_sr_t03" - Fragment Flurry Jess"
		"Hero:hid_outlander_013_sr_t04" - Fragment Flurry Jess"
		"Hero:hid_outlander_013_sr_t05" - Fragment Flurry Jess"
		"Hero:hid_outlander_013_stpatricks_sr_t01" - Staredown Southie
		"Hero:hid_outlander_013_stpatricks_sr_t02" - Staredown Southie
		"Hero:hid_outlander_013_stpatricks_sr_t03" - Staredown Southie
		"Hero:hid_outlander_013_stpatricks_sr_t04" - Staredown Southie
		"Hero:hid_outlander_013_stpatricks_sr_t05" - Staredown Southie
		"Hero:hid_outlander_013_vr_t01" - Fragment Flurry Jess"
		"Hero:hid_outlander_013_vr_t02" - Fragment Flurry Jess"
		"Hero:hid_outlander_013_vr_t03" - Fragment Flurry Jess"
		"Hero:hid_outlander_013_vr_t04" - Fragment Flurry Jess"
		"Hero:hid_outlander_013_vr_t05" - Fragment Flurry Jess"
		"Hero:hid_outlander_014_m_sr_t01" - Flash A.C."
		"Hero:hid_outlander_014_m_sr_t02" - Flash A.C."
		"Hero:hid_outlander_014_m_sr_t03" - Flash A.C."
		"Hero:hid_outlander_014_m_sr_t04" - Flash A.C."
		"Hero:hid_outlander_014_m_sr_t05" - Flash A.C."
		"Hero:hid_outlander_014_r_t01" - Fireflower Eagle Eye
		"Hero:hid_outlander_014_r_t02" - Fireflower Eagle Eye
		"Hero:hid_outlander_014_r_t03" - Fireflower Eagle Eye
		"Hero:hid_outlander_014_r_t04" - Fireflower Eagle Eye
		"Hero:hid_outlander_014_sr_t01" - Fireflower Eagle Eye
		"Hero:hid_outlander_014_sr_t02" - Fireflower Eagle Eye
		"Hero:hid_outlander_014_sr_t03" - Fireflower Eagle Eye
		"Hero:hid_outlander_014_sr_t04" - Fireflower Eagle Eye
		"Hero:hid_outlander_014_sr_t05" - Fireflower Eagle Eye
		"Hero:hid_outlander_014_vr_t01" - Fireflower Eagle Eye
		"Hero:hid_outlander_014_vr_t02" - Fireflower Eagle Eye
		"Hero:hid_outlander_014_vr_t03" - Fireflower Eagle Eye
		"Hero:hid_outlander_014_vr_t04" - Fireflower Eagle Eye
		"Hero:hid_outlander_014_vr_t05" - Fireflower Eagle Eye
		"Hero:hid_outlander_015_f_v1_r_t01" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_015_f_v1_r_t02" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_015_f_v1_r_t03" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_015_f_v1_r_t04" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_015_f_v1_sr_t01" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_015_f_v1_sr_t02" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_015_f_v1_sr_t03" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_015_f_v1_sr_t04" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_015_f_v1_sr_t05" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_015_f_v1_vr_t01" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_015_f_v1_vr_t02" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_015_f_v1_vr_t03" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_015_f_v1_vr_t04" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_015_f_v1_vr_t05" - T.E.D.D. Shot Jess"
		"Hero:hid_outlander_016_f_v1_sr_t01" - Ambush Buzz
		"Hero:hid_outlander_016_f_v1_sr_t02" - Ambush Buzz
		"Hero:hid_outlander_016_f_v1_sr_t03" - Ambush Buzz
		"Hero:hid_outlander_016_f_v1_sr_t04" - Ambush Buzz
		"Hero:hid_outlander_016_f_v1_sr_t05" - Ambush Buzz
		"Hero:hid_outlander_016_m_v1_sr_t01" - Shockgunner Grizzly
		"Hero:hid_outlander_016_m_v1_sr_t02" - Shockgunner Grizzly
		"Hero:hid_outlander_016_m_v1_sr_t03" - Shockgunner Grizzly
		"Hero:hid_outlander_016_m_v1_sr_t04" - Shockgunner Grizzly
		"Hero:hid_outlander_016_m_v1_sr_t05" - Shockgunner Grizzly
		"Hero:hid_outlander_016_m_v1_vr_t01" - Shockgunner Grizzly
		"Hero:hid_outlander_016_m_v1_vr_t02" - Shockgunner Grizzly
		"Hero:hid_outlander_016_m_v1_vr_t03" - Shockgunner Grizzly
		"Hero:hid_outlander_016_m_v1_vr_t04" - Shockgunner Grizzly
		"Hero:hid_outlander_016_m_v1_vr_t05" - Shockgunner Grizzly
		"Hero:hid_outlander_017_m_v1_sr_t01" - Wild Fragment Deadeye
		"Hero:hid_outlander_017_m_v1_sr_t02" - Wild Fragment Deadeye
		"Hero:hid_outlander_017_m_v1_sr_t03" - Wild Fragment Deadeye
		"Hero:hid_outlander_017_m_v1_sr_t04" - Wild Fragment Deadeye
		"Hero:hid_outlander_017_m_v1_sr_t05" - Wild Fragment Deadeye
		"Hero:hid_outlander_017_m_v1_vr_t01" - Wild Fragment Deadeye
		"Hero:hid_outlander_017_m_v1_vr_t02" - Wild Fragment Deadeye
		"Hero:hid_outlander_017_m_v1_vr_t03" - Wild Fragment Deadeye
		"Hero:hid_outlander_017_m_v1_vr_t04" - Wild Fragment Deadeye
		"Hero:hid_outlander_017_m_v1_vr_t05" - Wild Fragment Deadeye
		"Hero:hid_outlander_018_sr_t01" - Sanguine Dusk
		"Hero:hid_outlander_018_sr_t02" - Sanguine Dusk
		"Hero:hid_outlander_018_sr_t03" - Sanguine Dusk
		"Hero:hid_outlander_018_sr_t04" - Sanguine Dusk
		"Hero:hid_outlander_018_sr_t05" - Sanguine Dusk
		"Hero:hid_outlander_020_sr_t01" - Valkyrie Rio"
		"Hero:hid_outlander_020_sr_t02" - Valkyrie Rio"
		"Hero:hid_outlander_020_sr_t03" - Valkyrie Rio"
		"Hero:hid_outlander_020_sr_t04" - Valkyrie Rio"
		"Hero:hid_outlander_020_sr_t05" - Valkyrie Rio"
		"Hero:hid_outlander_021_sr_t01" - Ventura Ramirez
		"Hero:hid_outlander_021_sr_t02" - Ventura Ramirez
		"Hero:hid_outlander_021_sr_t03" - Ventura Ramirez
		"Hero:hid_outlander_021_sr_t04" - Ventura Ramirez
		"Hero:hid_outlander_021_sr_t05" - Ventura Ramirez
		"Hero:hid_outlander_022_sr_t01" - Subzero Zenith"
		"Hero:hid_outlander_022_sr_t02" - Subzero Zenith"
		"Hero:hid_outlander_022_sr_t03" - Subzero Zenith"
		"Hero:hid_outlander_022_sr_t04" - Subzero Zenith"
		"Hero:hid_outlander_022_sr_t05" - Subzero Zenith"
		"Hero:hid_outlander_023_sr_t01" - The Ice Queen"
		"Hero:hid_outlander_023_sr_t02" - The Ice Queen"
		"Hero:hid_outlander_023_sr_t03" - The Ice Queen"
		"Hero:hid_outlander_023_sr_t04" - The Ice Queen"
		"Hero:hid_outlander_023_sr_t05" - The Ice Queen"
		"Hero:hid_outlander_024_sr_t01" - Steel Wool Anthony
		"Hero:hid_outlander_024_sr_t02" - Steel Wool Anthony
		"Hero:hid_outlander_024_sr_t03" - Steel Wool Anthony
		"Hero:hid_outlander_024_sr_t04" - Steel Wool Anthony
		"Hero:hid_outlander_024_sr_t05" - Steel Wool Anthony
		"Hero:hid_outlander_025_pirateoutlander_sr_t01" - Crossbones Barret
		"Hero:hid_outlander_025_pirateoutlander_sr_t02" - Crossbones Barret
		"Hero:hid_outlander_025_pirateoutlander_sr_t03" - Crossbones Barret
		"Hero:hid_outlander_025_pirateoutlander_sr_t04" - Crossbones Barret
		"Hero:hid_outlander_025_pirateoutlander_sr_t05" - Crossbones Barret
		"Hero:hid_outlander_025_pirateoutlander_vr_t01" - Crossbones Barret
		"Hero:hid_outlander_025_pirateoutlander_vr_t02" - Crossbones Barret
		"Hero:hid_outlander_025_pirateoutlander_vr_t03" - Crossbones Barret
		"Hero:hid_outlander_025_pirateoutlander_vr_t04" - Crossbones Barret
		"Hero:hid_outlander_025_pirateoutlander_vr_t05" - Crossbones Barret
		"Hero:hid_outlander_026_bunnyoutlander_sr_t01" - Cottontail Eagle Eye
		"Hero:hid_outlander_026_bunnyoutlander_sr_t02" - Cottontail Eagle Eye
		"Hero:hid_outlander_026_bunnyoutlander_sr_t03" - Cottontail Eagle Eye
		"Hero:hid_outlander_026_bunnyoutlander_sr_t04" - Cottontail Eagle Eye
		"Hero:hid_outlander_026_bunnyoutlander_sr_t05" - Cottontail Eagle Eye
		"Hero:hid_outlander_027_dinooutlander_sr_t01" - Fossil Southie
		"Hero:hid_outlander_027_dinooutlander_sr_t02" - Fossil Southie
		"Hero:hid_outlander_027_dinooutlander_sr_t03" - Fossil Southie
		"Hero:hid_outlander_027_dinooutlander_sr_t04" - Fossil Southie
		"Hero:hid_outlander_027_dinooutlander_sr_t05" - Fossil Southie
		"Hero:hid_outlander_028_retroscifistoryoutlander_sr_t01" - Azalea Clark
		"Hero:hid_outlander_028_retroscifistoryoutlander_sr_t02" - Azalea Clark
		"Hero:hid_outlander_028_retroscifistoryoutlander_sr_t03" - Azalea Clark
		"Hero:hid_outlander_028_retroscifistoryoutlander_sr_t04" - Azalea Clark
		"Hero:hid_outlander_028_retroscifistoryoutlander_sr_t05" - Azalea Clark
		"Hero:hid_outlander_029_retroscifioutlander_sr_t01" - Cyberclops"
		"Hero:hid_outlander_029_retroscifioutlander_sr_t02" - Cyberclops"
		"Hero:hid_outlander_029_retroscifioutlander_sr_t03" - Cyberclops"
		"Hero:hid_outlander_029_retroscifioutlander_sr_t04" - Cyberclops"
		"Hero:hid_outlander_029_retroscifioutlander_sr_t05" - Cyberclops"
		"Hero:hid_outlander_029_retroscifioutlander_vr_t01" - Cyberclops"
		"Hero:hid_outlander_029_retroscifioutlander_vr_t02" - Cyberclops"
		"Hero:hid_outlander_029_retroscifioutlander_vr_t03" - Cyberclops"
		"Hero:hid_outlander_029_retroscifioutlander_vr_t04" - Cyberclops"
		"Hero:hid_outlander_029_retroscifioutlander_vr_t05" - Cyberclops"
		"Hero:hid_outlander_030_radoutlander_sr_t01" - Main Stage Quinn"
		"Hero:hid_outlander_030_radoutlander_sr_t02" - Main Stage Quinn"
		"Hero:hid_outlander_030_radoutlander_sr_t03" - Main Stage Quinn"
		"Hero:hid_outlander_030_radoutlander_sr_t04" - Main Stage Quinn"
		"Hero:hid_outlander_030_radoutlander_sr_t05" - Main Stage Quinn"
		"Hero:hid_outlander_030_radoutlander_vr_t01" - Main Stage Quinn"
		"Hero:hid_outlander_030_radoutlander_vr_t02" - Main Stage Quinn"
		"Hero:hid_outlander_030_radoutlander_vr_t03" - Main Stage Quinn"
		"Hero:hid_outlander_030_radoutlander_vr_t04" - Main Stage Quinn"
		"Hero:hid_outlander_030_radoutlander_vr_t05" - Main Stage Quinn"
		"Hero:hid_outlander_031_halloweenoutlander_sr_t01" - Willow"
		"Hero:hid_outlander_031_halloweenoutlander_sr_t02" - Willow"
		"Hero:hid_outlander_031_halloweenoutlander_sr_t03" - Willow"
		"Hero:hid_outlander_031_halloweenoutlander_sr_t04" - Willow"
		"Hero:hid_outlander_031_halloweenoutlander_sr_t05" - Willow"
		"Hero:hid_outlander_032_toyoutlander_sr_t01" - Jilly Teacup"
		"Hero:hid_outlander_032_toyoutlander_sr_t02" - Jilly Teacup"
		"Hero:hid_outlander_032_toyoutlander_sr_t03" - Jilly Teacup"
		"Hero:hid_outlander_032_toyoutlander_sr_t04" - Jilly Teacup"
		"Hero:hid_outlander_032_toyoutlander_sr_t05" - Jilly Teacup"
		"Hero:hid_outlander_033_kurohomura_sr_t01" - Kurohomura"
		"Hero:hid_outlander_033_kurohomura_sr_t02" - Kurohomura"
		"Hero:hid_outlander_033_kurohomura_sr_t03" - Kurohomura"
		"Hero:hid_outlander_033_kurohomura_sr_t04" - Kurohomura"
		"Hero:hid_outlander_033_kurohomura_sr_t05" - Kurohomura"
		"Hero:hid_outlander_034_period_fleming_sr_t01" - Undercover Buzz
		"Hero:hid_outlander_034_period_fleming_sr_t02" - Undercover Buzz
		"Hero:hid_outlander_034_period_fleming_sr_t03" - Undercover Buzz
		"Hero:hid_outlander_034_period_fleming_sr_t04" - Undercover Buzz
		"Hero:hid_outlander_034_period_fleming_sr_t05" - Undercover Buzz
		"Hero:hid_outlander_034_period_fleming_vr_t01" - Undercover Buzz
		"Hero:hid_outlander_034_period_fleming_vr_t02" - Undercover Buzz
		"Hero:hid_outlander_034_period_fleming_vr_t03" - Undercover Buzz
		"Hero:hid_outlander_034_period_fleming_vr_t04" - Undercover Buzz
		"Hero:hid_outlander_034_period_fleming_vr_t05" - Undercover Buzz
		"Hero:hid_outlander_035_palespooky_outlander_holiday_sr_t01" - Red Willow"
		"Hero:hid_outlander_035_palespooky_outlander_holiday_sr_t02" - Red Willow"
		"Hero:hid_outlander_035_palespooky_outlander_holiday_sr_t03" - Red Willow"
		"Hero:hid_outlander_035_palespooky_outlander_holiday_sr_t04" - Red Willow"
		"Hero:hid_outlander_035_palespooky_outlander_holiday_sr_t05" - Red Willow"
		"Hero:hid_outlander_035_palespooky_outlander_holiday_vr_t01" - Red Willow"
		"Hero:hid_outlander_035_palespooky_outlander_holiday_vr_t02" - Red Willow"
		"Hero:hid_outlander_035_palespooky_outlander_holiday_vr_t03" - Red Willow"
		"Hero:hid_outlander_035_palespooky_outlander_holiday_vr_t04" - Red Willow"
		"Hero:hid_outlander_035_palespooky_outlander_holiday_vr_t05" - Red Willow"
		"Hero:hid_outlander_036_dino_outlander_sr_t01" - Parasaur Jess"
		"Hero:hid_outlander_036_dino_outlander_sr_t02" - Parasaur Jess"
		"Hero:hid_outlander_036_dino_outlander_sr_t03" - Parasaur Jess"
		"Hero:hid_outlander_036_dino_outlander_sr_t04" - Parasaur Jess"
		"Hero:hid_outlander_036_dino_outlander_sr_t05" - Parasaur Jess"
		"Hero:hid_outlander_036_dino_outlander_vr_t01" - Parasaur Jess"
		"Hero:hid_outlander_036_dino_outlander_vr_t02" - Parasaur Jess"
		"Hero:hid_outlander_036_dino_outlander_vr_t03" - Parasaur Jess"
		"Hero:hid_outlander_036_dino_outlander_vr_t04" - Parasaur Jess"
		"Hero:hid_outlander_036_dino_outlander_vr_t05" - Parasaur Jess"
		"Hero:hid_outlander_037_fuzzy_bear_teddy_sr_t01" - Metal Team Leader
		"Hero:hid_outlander_037_fuzzy_bear_teddy_sr_t02" - Metal Team Leader
		"Hero:hid_outlander_037_fuzzy_bear_teddy_sr_t03" - Metal Team Leader
		"Hero:hid_outlander_037_fuzzy_bear_teddy_sr_t04" - Metal Team Leader
		"Hero:hid_outlander_037_fuzzy_bear_teddy_sr_t05" - Metal Team Leader
		"Hero:hid_outlander_037_fuzzy_bear_teddy_vr_t01" - Metal Team Leader
		"Hero:hid_outlander_037_fuzzy_bear_teddy_vr_t02" - Metal Team Leader
		"Hero:hid_outlander_037_fuzzy_bear_teddy_vr_t03" - Metal Team Leader
		"Hero:hid_outlander_037_fuzzy_bear_teddy_vr_t04" - Metal Team Leader
		"Hero:hid_outlander_037_fuzzy_bear_teddy_vr_t05" - Metal Team Leader
		"Hero:hid_outlander_038_clip_sr_t01" - Cassie \"Clip\" Lipman"
		"Hero:hid_outlander_038_clip_sr_t02" - Cassie \"Clip\" Lipman"
		"Hero:hid_outlander_038_clip_sr_t03" - Cassie \"Clip\" Lipman"
		"Hero:hid_outlander_038_clip_sr_t04" - Cassie \"Clip\" Lipman"
		"Hero:hid_outlander_038_clip_sr_t05" - Cassie \"Clip\" Lipman"
		"Hero:hid_outlander_038_clip_vr_t01" - Cassie \"Clip\" Lipman"
		"Hero:hid_outlander_038_clip_vr_t02" - Cassie \"Clip\" Lipman"
		"Hero:hid_outlander_038_clip_vr_t03" - Cassie \"Clip\" Lipman"
		"Hero:hid_outlander_038_clip_vr_t04" - Cassie \"Clip\" Lipman"
		"Hero:hid_outlander_038_clip_vr_t05" - Cassie \"Clip\" Lipman"
		"Hero:hid_outlander_039_female_gumshoe_sr_t01" - Gumshoe
		"Hero:hid_outlander_039_female_gumshoe_sr_t02" - Gumshoe
		"Hero:hid_outlander_039_female_gumshoe_sr_t03" - Gumshoe
		"Hero:hid_outlander_039_female_gumshoe_sr_t04" - Gumshoe
		"Hero:hid_outlander_039_female_gumshoe_sr_t05" - Gumshoe
		"Hero:hid_outlander_039_female_gumshoe_vr_t01" - Gumshoe
		"Hero:hid_outlander_039_female_gumshoe_vr_t02" - Gumshoe
		"Hero:hid_outlander_039_female_gumshoe_vr_t03" - Gumshoe
		"Hero:hid_outlander_039_female_gumshoe_vr_t04" - Gumshoe
		"Hero:hid_outlander_039_female_gumshoe_vr_t05" - Gumshoe
		"Hero:hid_outlander_myth02_sr_t01" - Ragnarok
		"Hero:hid_outlander_myth02_sr_t02" - Ragnarok
		"Hero:hid_outlander_myth02_sr_t03" - Ragnarok
		"Hero:hid_outlander_myth02_sr_t04" - Ragnarok
		"Hero:hid_outlander_myth02_sr_t05" - Ragnarok
		"Hero:hid_outlander_myth03_sr_t01" - Field Agent Rio"
		"Hero:hid_outlander_myth03_sr_t02" - Field Agent Rio"
		"Hero:hid_outlander_myth03_sr_t03" - Field Agent Rio"
		"Hero:hid_outlander_myth03_sr_t04" - Field Agent Rio"
		"Hero:hid_outlander_myth03_sr_t05" - Field Agent Rio"
		"Hero:hid_outlander_punchdamage_sr_t01" - Striker A.C."
		"Hero:hid_outlander_punchdamage_sr_t02" - Striker A.C."
		"Hero:hid_outlander_punchdamage_sr_t03" - Striker A.C."
		"Hero:hid_outlander_punchdamage_sr_t04" - Striker A.C."
		"Hero:hid_outlander_punchdamage_sr_t05" - Striker A.C."
		"Hero:hid_outlander_punchdamage_vr_t01" - Striker A.C."
		"Hero:hid_outlander_punchdamage_vr_t02" - Striker A.C."
		"Hero:hid_outlander_punchdamage_vr_t03" - Striker A.C."
		"Hero:hid_outlander_punchdamage_vr_t04" - Striker A.C."
		"Hero:hid_outlander_punchdamage_vr_t05" - Striker A.C."
		"Hero:hid_outlander_punchphase_r_t01" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_r_t02" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_r_t03" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_r_t04" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_sr_t01" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_sr_t02" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_sr_t03" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_sr_t04" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_sr_t05" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_uc_t01" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_uc_t02" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_uc_t03" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_vr_t01" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_vr_t02" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_vr_t03" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_vr_t04" - Shock Specialist A.C."
		"Hero:hid_outlander_punchphase_vr_t05" - Shock Specialist A.C."
		"Hero:hid_outlander_sony_r_t01" - Trailblazer A.C."
		"Hero:hid_outlander_sony_r_t02" - Trailblazer A.C."
		"Hero:hid_outlander_sony_r_t03" - Trailblazer A.C."
		"Hero:hid_outlander_sony_r_t04" - Trailblazer A.C."
		"Hero:hid_outlander_sony_sr_t01" - Trailblazer A.C."
		"Hero:hid_outlander_sony_sr_t02" - Trailblazer A.C."
		"Hero:hid_outlander_sony_sr_t03" - Trailblazer A.C."
		"Hero:hid_outlander_sony_sr_t04" - Trailblazer A.C."
		"Hero:hid_outlander_sony_sr_t05" - Trailblazer A.C."
		"Hero:hid_outlander_sony_vr_t01" - Trailblazer A.C."
		"Hero:hid_outlander_sony_vr_t02" - Trailblazer A.C."
		"Hero:hid_outlander_sony_vr_t03" - Trailblazer A.C."
		"Hero:hid_outlander_sony_vr_t04" - Trailblazer A.C."
		"Hero:hid_outlander_sony_vr_t05" - Trailblazer A.C."
		"Hero:hid_outlander_spherefragment_r_t01" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_r_t02" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_r_t03" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_r_t04" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_sr_t01" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_sr_t02" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_sr_t03" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_sr_t04" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_sr_t05" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_uc_t01" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_uc_t02" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_uc_t03" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_vr_t01" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_vr_t02" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_vr_t03" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_vr_t04" - Trailblazer Quinn"
		"Hero:hid_outlander_spherefragment_vr_t05" - Trailblazer Quinn"
		"Hero:hid_outlander_xbox_r_t01" - Trailblazer Jess"
		"Hero:hid_outlander_xbox_r_t02" - Trailblazer Jess"
		"Hero:hid_outlander_xbox_r_t03" - Trailblazer Jess"
		"Hero:hid_outlander_xbox_r_t04" - Trailblazer Jess"
		"Hero:hid_outlander_xbox_sr_t01" - Trailblazer Jess"
		"Hero:hid_outlander_xbox_sr_t02" - Trailblazer Jess"
		"Hero:hid_outlander_xbox_sr_t03" - Trailblazer Jess"
		"Hero:hid_outlander_xbox_sr_t04" - Trailblazer Jess"
		"Hero:hid_outlander_xbox_sr_t05" - Trailblazer Jess"
		"Hero:hid_outlander_xbox_vr_t01" - Trailblazer Jess"
		"Hero:hid_outlander_xbox_vr_t02" - Trailblazer Jess"
		"Hero:hid_outlander_xbox_vr_t03" - Trailblazer Jess"
		"Hero:hid_outlander_xbox_vr_t04" - Trailblazer Jess"
		"Hero:hid_outlander_xbox_vr_t05" - Trailblazer Jess"
		"Hero:hid_outlander_zonefragment_sr_t01" - Phase Scout Jess"
		"Hero:hid_outlander_zonefragment_sr_t02" - Phase Scout Jess"
		"Hero:hid_outlander_zonefragment_sr_t03" - Phase Scout Jess"
		"Hero:hid_outlander_zonefragment_sr_t04" - Phase Scout Jess"
		"Hero:hid_outlander_zonefragment_sr_t05" - Phase Scout Jess"
		"Hero:hid_outlander_zoneharvest_blockbuster_sr_t01" - Archaeolo-Jess"
		"Hero:hid_outlander_zoneharvest_blockbuster_sr_t02" - Archaeolo-Jess"
		"Hero:hid_outlander_zoneharvest_blockbuster_sr_t03" - Archaeolo-Jess"
		"Hero:hid_outlander_zoneharvest_blockbuster_sr_t04" - Archaeolo-Jess"
		"Hero:hid_outlander_zoneharvest_blockbuster_sr_t05" - Archaeolo-Jess"
		"Hero:hid_outlander_zoneharvest_r_t01" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_r_t02" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_r_t03" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_r_t04" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_sr_t01" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_sr_t02" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_sr_t03" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_sr_t04" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_sr_t05" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_uc_t01" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_uc_t02" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_uc_t03" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_vr_t01" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_vr_t02" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_vr_t03" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_vr_t04" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvest_vr_t05" - Pathfinder Jess"
		"Hero:hid_outlander_zoneharvesthw_sr_t01" - Bloodfinder A.C."
		"Hero:hid_outlander_zoneharvesthw_sr_t02" - Bloodfinder A.C."
		"Hero:hid_outlander_zoneharvesthw_sr_t03" - Bloodfinder A.C."
		"Hero:hid_outlander_zoneharvesthw_sr_t04" - Bloodfinder A.C."
		"Hero:hid_outlander_zoneharvesthw_sr_t05" - Bloodfinder A.C."
		"Hero:hid_outlander_zonepistol_r_t01" - Ranger Deadeye
		"Hero:hid_outlander_zonepistol_r_t02" - Ranger Deadeye
		"Hero:hid_outlander_zonepistol_r_t03" - Ranger Deadeye
		"Hero:hid_outlander_zonepistol_r_t04" - Ranger Deadeye
		"Hero:hid_outlander_zonepistol_sr_t01" - Ranger Deadeye
		"Hero:hid_outlander_zonepistol_sr_t02" - Ranger Deadeye
		"Hero:hid_outlander_zonepistol_sr_t03" - Ranger Deadeye
		"Hero:hid_outlander_zonepistol_sr_t04" - Ranger Deadeye
		"Hero:hid_outlander_zonepistol_sr_t05" - Ranger Deadeye
		"Hero:hid_outlander_zonepistol_vr_t01" - Ranger Deadeye
		"Hero:hid_outlander_zonepistol_vr_t02" - Ranger Deadeye
		"Hero:hid_outlander_zonepistol_vr_t03" - Ranger Deadeye
		"Hero:hid_outlander_zonepistol_vr_t04" - Ranger Deadeye
		"Hero:hid_outlander_zonepistol_vr_t05" - Ranger Deadeye
		"Hero:hid_outlander_zonepistolhw_sr_t01" - Beetlejess"
		"Hero:hid_outlander_zonepistolhw_sr_t02" - Beetlejess"
		"Hero:hid_outlander_zonepistolhw_sr_t03" - Beetlejess"
		"Hero:hid_outlander_zonepistolhw_sr_t04" - Beetlejess"
		"Hero:hid_outlander_zonepistolhw_sr_t05" - Beetlejess"
		"Hero:hid_outlander_zonepistolhw_vr_t01" - Beetlejess"
		"Hero:hid_outlander_zonepistolhw_vr_t02" - Beetlejess"
		"Hero:hid_outlander_zonepistolhw_vr_t03" - Beetlejess"
		"Hero:hid_outlander_zonepistolhw_vr_t04" - Beetlejess"
		"Hero:hid_outlander_zonepistolhw_vr_t05" - Beetlejess"

(Note: this list wasn't written by me. Thank you to whoever sent me this on discord!)

P.S I researched all of this out of spite of gatekeepers acting like assholes to those asking how to do this 
(as well as ripping ppl off by selling it for $50 or scamming as well)
