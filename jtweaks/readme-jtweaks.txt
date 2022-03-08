jmerry's Tweak Collection

Version 1.0

Overview: This mod is a WeidDU compilation of fixes, rule tweaks, and a few bits of truly altered content. Some of it is stuff I've used in my own games, while other parts are newly written now that I have the tools. I've tried to stay out of the way of the larger Tweaks Anthology, as I could just include that mod's components instead.

The line between "bug fixes" and "rule changes" is subjective; I intent to use all of the "bug fixes" myself, but not all of the "rule changes".

General Compatibility:
This mod works only on the Baldur's Gate Enhanced Edition games; Baldur's Gate: Enhanced Edition, Baldur's Gate II: Enhanced Edition, and the Enhanced Edition Trilogy conversion project. It is designed for the 2.6 patch released in 2021, and contains a number of components dealing with Enhanced Edition content or matters changed in that patch.

Not all components apply to all games; if a component does not apply to your game, it will be automatically skipped.

As I don't have Siege of Dragonspear or EET myself, the mod is entirely untested for games of BGEE containing SoD or for EET games. Please report any errors to close this gap.

As a tweak collection, this mod should be installed last or nearly last. Whenever possible, it attempts to alter existing game resources in an interactive way.

Installation:

This mod is distributed as a zip archive with Mac and Windows installers included. Unpack it, then put the jtweaks folder and any installers you intend to use in your game folder.
Mac OS X: Put setup-jtweaks and setup-jtweaks.command from the install-osx folder in your game folder, and run setup-jtweaks.command. On recent OS versions, you'll need to go to System Preferences/Security to give it permission. (Unidentified developer)
Windows: Put setup-jtweaks.exe from the install-windows folder in your game folder, and run it. This has not been tested, as I don't have a Windows system.
Any: You can also run any WeiDU install tool you want; I use subtledoctor's Mac WeiDU Launcher. If you do this, you need WeiDU version 247 or later, with 248 or later recommended.

Special Note for Siege of Dragonspear from Steam/GOG
Good Old Games (GOG) and Steam both package the additional content for Siege of Dragonspear in a method that WeiDU, the tool used to install this mod, cannot access. You must run a program called Modmerge on your SoD installation before you can install this or any other WeiDU-based mod.

Specific component details and individual component compatibility notes:

Bug Fixes:

– Wilson's strength doesn't stack indefinitely
Games: BG2EE, EET

In BG2EE, you can recruit the bear Wilson to your party. He has a unique kit that, among other things, increases his strength as he gains levels. Unfortunately, the spell that does that is bugged, and applies additional strength boosts every time he leaves and rejoins the party. Even the version of him with the lowest possible level can be quickly brought to strength 25 by simply dismissing and re-accepting him repeatedly.
This component fixes that issue, so his strength stays at the intended levels.

– Vernus can be raised
Games: BG2EE, EET
Patch: 2.6

In Dorn's quest during the SoA campaign, you encounter at one point a "dead" druid Vernus that you can raise to use as a sacrifice. Sadly, the update to resurrection spells in patch 2.6 broke the mechanism used for this.
This component restores the ability to raise Vernus by altering those spells again.

– Fix Black Pits oversights:
Games: BGEE, EET

This component fixes several minor issues with the Black Pits adventure bundled with BGEE.
– The Black Pits shops include an Improved Cloak of Protection +2, which is even better than it should be because it can be used with enchanted armor or another protection item. This component adds that item to the exclusion list if it isn't there already.
– If you export a character from the Black Pits to play in the main campaign, they retain an override script used to support the arena fights. This can cause unintended effects, especially if the character ever drops to 1 HP.
This component fixes that issue, causing the script to remove itself if the character is not in a Black Pits area.
– In the final normal fight, your foe Hogarl has both potions of extra healing and potions of fire breath. When he's hurt and has at least one potion of extra healing, he's scripted to ... use a potion of fire breath?
This component fixes that obvious mistake, so Hogarl uses the potions he's meant to. He should be slightly tougher now.
- The Black Pits shops include the Sandthief's Ring at both tier 2 and tier 3. The tier 2 version was fully charged, while the tier 3 version forgot to set a charge number. This component updates the tier 3 version to be fully charged as well. The ring is still never worth buying, because there's an unlimited supply of invisibility potions as well for a much lower price.

– Enchant Weapon works in contingencies
Games: BGEE, BG2EE, EET

The Enchant Weapon spell, in the EE, modifies your existing attacks to use the new +3 enchantment value when that's higher. However, when used in a contingency, an older implementation of the spell that creates a temporary +3 weapon is used instead.
This component fixes that issue so that Enchant Weapon behaves exactly the same in contingencies as it does when cast normally.

– Joinable NPCs don't have null kits
Games: BGEE, BG2EE, EET

Many NPCs have null (kit ID 0) kits, instead of the standard "base class" kit that a player-created character gets if they don't otherwise select a kit. In most cases, this is irrelevant. However, if a character (such as Imoen) with a null kit is capable of learning arcane spells, they are treated as a specialist with no school for the purpose of spell learning, and take a 15% penalty to their spell learning chance for all scrolls.
This component takes all joinable characters with null kits and gives them the "base class" kit. (It may also apply the change to some characters that can't actually join, but that's completely harmless)

– NPCs don't go in inaccessible locations
Games: BG2EE, EET

A few NPCs in SoA are initially placed in walls, making them difficult to interact with. This component moves them to accessible locations nearby. In addition, at certain points of her dialogue, Aerie storms off to an inaccessible location on the circus tent map. In at least one case, she even says she's going back to the circus. This component sends her to her usual spot inside the tent when that happens instead.
This component may result in you facing an interesting encounter you haven't seen before; there's a man named Stein in the graveyard district at night.

– Close polymorph immunity loopholes
Games: BGEE, BG2EE, EET

A number of monsters are immune to polymorphs. However, the actual polymorph effect is not the only effect of hostile polymorph spells, and so they need specific immunities to those spells as well. This leads to some loopholes, notably with the wand of polymorphing. You can hit a demon with the wand to reduce them to 5 HP, 3 strength, no chance of casting arcane or divine spells, and 1d2 base damage even though they're supposed to be immune.
This component alters everything that grants polymorph immunity to grant full immunity to the effects of the wand and bolt of polymorphing, and adds an overlooked wild surge to the immunity list. In addition, such items and spells formerly granted immunity to Sphere of Chaos; they now only grant immunity to the sphere's polymorph effect.

Compatibility note: this component adds new subspells in the base game's namespace. WAND09.SPL for the effect of WAND09.ITM, BOLT05.SPL for the effect of BOLT05.ITM, and SPWI711P.SPL for the polymorph effect of SPWI711. If the subspell in question already exists, the component skips making any changes for that effect.

– Shapeshift corrections
Games: BGEE, BG2EE, EET
Patch: 2.6

Voluntary shapeshifting has long been prone to bugs, and the 2.6 update is no exception. While the crashes that plagued earlier versions seem to have been fixed, there are still plenty of mismatches between spell descriptions and actual effects. This component seeks to fix as many of them as possible.
In BGEE:
– Druid wolf shapeshifts used the wrong kind of wolf, resulting in strength 18 and dex 17 instead of 15 and 18 as listed. This component switches that, and also adds +1 damage like mage wolf polymorphs get.
– Druid greater werewolf form doesn't match the BG2EE version; it lacks the regeneration added in version 2.6. This component adds that regeneration, although it doesn't matter in the standard rules.
- Many form descriptions are updated to provide more accurate and complete information.
- Shapeshift forms no longer allow for off-hand weapons to be used. This may display incorrectly on the inventory screen, but only main-hand attacks will actually happen and weapons held in the off hand will not provide passive bonuses.
In BG2EE:
– Black and brown bear shapeshifts were inadvertently switched with the 2.6 update; you use the ability for one kind of bear and get the other instead. This component switches them back.
– Druid wolf shapeshifts used the wrong kind of wolf, resulting in strength 18 and dex 17 instead of 15 and 18 as listed. This component switches that, and also adds +1 damage like mage wolf polymorphs get.
– The weapon for the mage's ogre polymorph wasn't flagged as magical, unlike in BGEE. This component fixes that.
– The two mage bear polymorphs used the same bear; this component makes them actually differ.
– Shapechange forms with immunity to +1 and greater weapons had only the highest weapon immunity effect, rather than the full array of support effects (such as normal weapon immunity and scripting states). This component adds those effects back in, so that things work better with other effects that key off that immunity.
– Iron Golem form lacked almost all of the immunities claimed in its description. This component adds them in.
– Many form descriptions are updated to provide more accurate and complete information.

This component comes in three versions: all forms, druid forms only, mage forms only. If you have another mod that alters shapeshifting, avoid using this component to alter any of the same forms that one did; this component's new descriptions may overwrite description changes from the other mod.
Item-based shapeshifts, such as from the Cloak of the Wolf, are unchanged.

– Wish Hardiness doesn't stack with itself
Games: BG2EE, EET

The Wish option "All party members gain the temporary ability Hardiness" is bugged. While Hardiness is supposed to remove existing instances of Hardiness and Defensive Stance, this version gets that wrong. It applies Hardiness to the party and removes it from the caster. The same spell could result in one character going from one instance of Hardiness to none and another going from one to two (caster is a clone of a fighter/mage with Hardiness active, at least one party member has Hardiness active).
This spell corrects that mismatch, so that Wish Hardiness removes Hardiness from the same targets it benefits.

– Hold Person doesn't display multiple strings
Games: BGEE, BG2EE, EET

When Hold Person is cast successfully, two instances of the string "Held" appear. One comes from the game engine, while the other is an explicit effect of the spell. This component removes that explicit effect so that only one string appears.

– Barbarian Rage blocks cosmetic strings
Games: BGEE

The BGEE version of a barbarian's Rage fails to block several cosmetic effects that it should, such as the "Held" string and the overhead icon for Horror. This component corrects that issue.

– Dueling fireshields don't go infinite
Games: BGEE, BG2EE, EET
Patch: 2.6

The 2.6 patch updated fireshields in several ways, one of which was to route the retaliation damage through a new projectile. This has an unintended side effect; if one creature with a fireshield up hits another, damage bounces back and forth every tick until either one of the creatures is dead or they're out of range of each other.
This component fixes that issue, reverting "dueling fireshields" to the older behavior of delivering exactly one hit each way.

– Standardize Wand of Missiles
Games: BGEE

Imoen and Mordaine (from the "combat testing" party in Candlekeep) start with wands of Magic Missiles. What you might not notice is that they aren't the same as all of the other wands of Magic Missiles in the game; they're technically a different item, and they lack the effect that allows Shield to block them.
This component standardizes Imoen and Mordaine to use the same Wand of Magic Missiles as everybody else.

- Nature's Beauty blindness can be cured
Games: BGEE, BG2EE, EET

The 7th level druid spell Nature's Beauty inflicts permanent blindness with no save. This is intended to be curable and dispellable, but the effect is unfortunately bugged. While the "Blinded" portrait icon can be dispelled or removed with an effect such as Cure Disease, and the character's vision radius can be restored with a Cure Disease effect, the 4-point penalties to base (unarmored) AC and to THAC0 are completely unremovable; they're applied to the creature's base stats.
This component restores the intended dispel/cure behavior by making the blindness technically temporary. It'll wear off ... in about eleven game years. Just cure it already. Clones of the spell - anything with the same permanent blindness effect - will also be patched.

Nature's Beauty is a party-friendly spell, and the only enemy that uses it in the vanilla campaign is the immortal version of Faldorn at the Druid Grove. As such, you are unlikely to notice the effect of this component unless you have a mod that changes enemy spellcasting behavior.

I have previously posted a quick and dirty "drop in override" version of this on the Beamdog and Gibberlings 3 forums. This version comes with better compatibility (no string errors on non-BG2EE games, no overwriting other modded effects of the spell) and a larger duration number.


Rule Changes:


- Temple cures work better
Games: BGEE, BG2EE, EET

Due to a quirk of the engine, when you buy a cure from a temple, the recipient is treated as the caster. This has troublesome implications for the function of some of the spells involved. Restoration spells fatigue the recipient, and dispels are frequently completely ineffective because the recipient casts them at level 1 when they're not a priest.
This component changes the spells most affected by this issue; temple Dispel Magic is changed to a single-target spell that always dispels, and the fatigue effect is removed from the temple versions of Lesser Restoration and Greater Restoration.

- Bala's Axe dispels reasonably well
Games: BGEE, BG2EE, EET

Another one for dispel levels. The 1/day Dispel Magic ability on Bala's Axe: Wizard Slayer uses the priest Dispel Magic Spell, at the wielder's divine caster level. Unless the wielder is a Shaman, you're pretty much out of luck.
This component changes that spell to an innate one, now cast at the wielder's innate caster level. You will now have a reasonable chance at dispelling effects with it.

- Celestials cast all of their spells at high levels
Games: BG2EE, EET

Devas and planetars have both cleric and mage spells. Devas are pure clerics, and thus cast their mage spells at minimum level. Planetars are pure mages, and thus cast their cleric spells at minimum level. This component turns them all into cleric/mages, so they cast all of their spells at high levels.
In addition, deva and planetar weapons both have a chance to dispel on hit ... at what appears to be a pretty low level. This component changes those weapons to dispel at level 25 (their standard creature level). One bone for the poor victims, though ... I've moved the dispel effect to the end of the list. Now, if you have a Death Ward up and a planetar rolls a vorpal hit, the Death Ward will block the instant death effect before being dispelled. Before, a planetar could dispel your Death Ward and decapitate you in the same attack.

- Antimagic rays and Spell Shield
Games: BGEE, BG2EE, EET

Beholder antimagic rays ignore almost all spell defenses, and go on to dispel the target of all combat protections (and anything else dispellable). There's just one exception - Spell Shield. Which works way too well. Spell Shield will not only block an antimagic ray, it will stick around to block the next. And all the rest for its full duration, unless some other spell breaks the shield.
This component changes that interaction, with two options.
- Antimagic rays ignore Spell Shield: Like it says, the antimagic ray goes right through the spell shield. The shield stays, but doesn't protect you from the ray. Unless it's a Hive Mother's ray; that will wipe out the shield and any other spell protections with it.
- Spell Shield blocks one antimagic ray: For this one, Spell Shield works against antimagic rays exactly like it does against conventional spell-breakers like Secret Word or Khelben's Warding Whip. It blocks one ray entirely, then goes away.

- Death Ward protects against Aec'Letec's Death Gaze
Games: BGEE, EET

Aec'Letec's Death Gaze has several effects if you fail the save: it paralyzes you, it inflicts the "dying" portrait icon, and after a delay it kills you and replaces you with a ghast. Absolutely nothing protects against the death and replacement effect, not even story mode; your only options are to save against it, to block it with a potion of mirrored eyes, or to dispel it during that delay.
Death Ward blocks the "dying" portrait icon. Which doesn't seem to be used by anything else.
This component changes Death Ward, and anything else that blocks the "dying" portrait icon, to also fully block the effects of Aec'Letec's gaze. This includes Story Mode; I believe that's the only other option for a player character within the standard BGEE rules and content.

- Elemental protection spells increment resistances
Games: BGEE, BG2EE, EET

A number of spells in the game temporarily boost resistances to various elements. Some of them increment resistances, while others set base resistances. The latter option plays badly with shapeshifting, as the most recent "set" effect wins and polymorphs effectively set all base resistances to the new creature's values. It's pretty inconsistent, too - priest Protection From Fire is an "increment" effect, while wizard Protection from Fire is a "set" effect.
This component standardizes all such spells to increment resistances, generally making them better.

- Vorpal weapons don't chunk
Games: BGEE, BG2EE, EET

This component simply changes all "vorpal" effects on weapons (instant death) to cause a normal death that allows resurrection rather than an exploding death that doesn't.
While you don't encounter any vorpal weapons in the standard BGEE campaign, there are still some resources for them in the game. As such, I'm allowing this component to install on BGEE, even if it doesn't do anything relevant.

- Resurrection can heal the living
Games: BGEE, BG2EE, EET
Patch: 2.6

The 2.6 update to resurrection spells removed the ability of Resurrection, Mass Raise Dead, and the Rod of Resurrection to heal living creatures. This component restores that ability.
It does not restore the bugged behavior of Mass Raise Dead that caused it to massively heal the party for up to 6 times the intended amount, or the various bugs regarding temporary abilities that inspired the update in the first place.

Compatibility note: this component adds new subspells in the base game's namespace. BHAAL4AH for the ToB Bhaalspawn resurrection power (unused in vanilla), SPPR712H for Resurrection and the Rod of Resurrection, SPPR729H for Mass Raise Dead. If any of these subspells already exist, the component will skip modifying the corresponding spells/items.

- Loosen restrictions on what clones can do
Games: BGEE, BG2EE, EET
Patch: 2.6

The 2.6 update tweaked the various clone effects in the game, adding significant restrictions on what clones can do. In standard 2.6, clones (such as those created by Project Image and Simulacrum) are unable to hide, search for traps, create clones, set up sequencers, or set contingencies.
This component loosens those restrictions, allowing clones to hide, search for traps, set up sequencers, and create contingencies. On the flip side, it prevents clones from using the "Thieving" ability to disarm traps, pick locks, or pick pockets. As the game engine already prevents clones from interacting with doors, containers, or floor regions, this only really blocks Pick Pockets. That ability could cause real problems; if a clone steals a critical item and then expires, the item in question is gone forever.

- Undead Hunters are better at Turn Undead
Games: BGEE, BG2EE, EET

This component adds a third advantage to the Undead Hunter kit; their Turn Undead ability is improved to approximately match that of a cleric with the same amount of experience.
I previously posted a quick and dirty version of this on the Beamdog forums; this is an improved version, using WeiDU for better installation and also updating the kit description.

- Loosen NPC item restrictions
Games: BGEE, BG2EE, EET

This component reduces the overly-specific class/kit/alignment restrictions on many NPC-specific items to reasonable levels, and also removes some attribute restrictions not listed in the item descriptions. It does not do anything about the items' restriction to only that NPC, and in some cases even tightens that (Cernd's staff is now listed in the item_use table in place of the second instance of Keldorn's sword, and both of Haer'Dalis' swords have tiefling-only restrictions instead of just one of them).
The only BGEE item affected by this mod is Eldoth's variety of poisoned arrow.

This component is primarily intended for use with mods that allow you to customize NPCs; it will have essentially no non-cosmetic effects under the standard rules.

- Green Slime poison can be cured
Games: BGEE, BG2EE, EET

If you get poisoned by a Green Slime, a simple antidote will stop the damage over time ... but it won't stop you from dying a few seconds later. This component changes that, so anything which cures poison will prevent the affected character from dying if delivered in time.
You still can't save the bartender at Ye Olde Inn, though. You just didn't get there fast enough.

- Potion effects don't stack with themselves
Games: BGEE, BG2EE, EET

When 2.6 was being developed, one beta version removed the ability of buff potions to stack with themselves. This change was dropped due to player response before the final release. But you know, I feel a bit bad about the part I played in that. So here's a simple mod component to apply that change.

With this component, drinking a potion with ongoing effects while already under the effect of a potion of the same type will merely refresh that effect's duration, rather than stacking the effect higher. If you drink two different potions with similar effects, the effects will stack; a potion of genius and a potion of mind focusing together will still give you +7 Int as long as both are active. However, drinking three potions of genius will only result in +4 Int, rather than +12 as in the unmodified game.

A few potions generate spurious matches; healing potions have a short-duration visual effect that the code catches. This shouldn't cause any actual problems, as permanent effects such as healing don't get removed.


Content Changes:


- Barrityl's Bigger and Better Burden
Games: BGEE, EET

In my latest full run of BGEE, I ran an evil party including Baeloth. I tried out his ring's ability to gamble on creating a gem, and ... it's disappointing. Only the three cheapest gems are even possible to get.
This component changes that gamble to be significantly more exciting; you can get gems up to a Black Opal in value. But beware - the damage you take if the attempt fails is also increased.
With this component, there is approximately a 1/3 chance of getting a gem. If you don't, you take 1d12 damage of a random element.

Compatibility note: this component overwrites any existing modifications to Baeloth's ring BARING.ITM. Do not use if you've already altered the item.

- Allies against Bodhi are better prepared against vampires
Games: BG2EE, EET

This component makes slight improvements to all three parties of potential allies in the fight against Bodhi.
- The paladin leader, Eric Vanstraaten, is now an Undead Hunter and gains the passive benefits of that kit.
- The thief leader, Arkanis Gath, now has an (undroppable) Amulet of Power so he can't be level-drained into oblivion.
- Drizzt's companion Wulfgar can now hit vampires with his hammer Aegis-fang +3; it was inexplicably set to enchantment level 0 before.
(Drizzt already has an undroppable Amulet of Power; he doesn't need any help.)

- Noober's Game
Games: BG2EE, EET

Buried deep within the files for the Black Pits 2, there is a hidden extra tier of fights after the final confrontation with Dennaton's forces. Disregarding all logic, you can battle friends and foes alike from the main campaign. Or you could, if the enemies had the proper scripts and any of this were enabled. But at the very end ... well, I'll leave it to the new announcer Elgiad:
"Well done! You have faced all manner of creature—heroic mortals, reprehensible villains, fiends, even a god—and defeated them all. It's tempting to simply declare you victorious, but there's still one challenger so vile, so reprehensible, and so feared that ALL who encounter him flee in screaming irritation!"
"I will not lie, he causes even me to recoil in horror. But to be the best, you must beat the worst. And so I give you... your final challenge!"
(These lines are fully voiced and wonderfully hammy. If you have Near Infinity or a similar tool to listen to them, they're strings 100794 and 100795)

That final challenger is ... Noober. Who talks to you. But beware - he has the largest dialogue file in the game that doesn't belong to a companion with a romance. And it's all one conversation. This is the largest and most complex conversation in the game, by far.
What is that conversation? It's a game - a fully realized text adventure game. I've previously brought that game out to be played in a thread on the Beamdog forums, and here it is in the main campaign. The bartender in Amkethran has a new scroll in his shop...
A number of small changes have been made from the original version of the conversation; fixes to incorrect string references, flow corrections, a few new reply options, and a rebalancing of the random elements (all in the player's favor).

- Bigger random spawns
Games: BGEE, BG2EE, EET

Particularly in BG1 wilderness maps, many monsters are generated by "spawn points". A monster type is chosen, and a number of monsters of that type based on the party's size and level spawns in. Unfortunately, many of these spawns are capped at disappointingly small numbers; even if you visit the gnoll fortress with a maxed-out party, you'll only see four gnolls or xvarts per spawn point.

This component raises those caps. If you've got the levels for it, you'll see groups of up to ten monsters of the same type.

This has minimal effect on the other campaigns, as they utilize a different system for most monster spawns. While there are still spawn points in BG2EE, most of them generate tokens such as "rdgob" which unpack to groups of creatures - in that case, two archer goblins and four melee goblins. Spawn points of this type are unchanged.

Disclaimer: This has not been tested for balance. At all. But you should be able to mow through packs of low-level enemies anyway, shouldn't you?


AI tweaks:


- Slightly improved party AI
Games: BGEE, BG2EE, EET

If you change an NPC's class, including by dual-classing them, the character is often unable to automatically use the new class's abilities with "Advanced AI". This component aims to address that, along with generally improving the logic for how to use such abilities.
- Find Traps: No change to the script conditions (use when not in combat), but all characters now have the block for it.
- Hide in Shadows: Shadowdancers will automatically hide in shadows even when near enemies. All other thieves, monks, and rangers will only do so when no enemies are near them. All characters now have this block.
- Bard Song/Shaman Dance: Jesters and Shamans will sing/dance when in combat and stop once combat ends. Other bards will sing regardless of combat status, unless they're invisible. All characters now have this block.
- Turn Undead: Characters will actually use this now; the trigger condition is no longer so difficult as to be practically impossible. All characters now have this block.
- Auto-attack: All characters now have the same blocks, instead of having one of five different variants. No real change to the logic here; I just standardized.

Compatibility note: Attempting to install this component on top of any modification of the script logic for any of these five actions is likely to break things. If you're lucky, this component will simply do nothing. If you're not, characters could forget how to perform these actions automatically at all. Don't risk it.
The scripts modified by this component are bddefai.bcs (player characters) and bd*****c.bcs (joinable NPCs) as referenced in PARTYAI.2DA. Scripts for the SoD-only joinables (Caelar, Corwin, Glint, M'Khiin, Voghiln) are excluded, since I don't know exactly what's in them.


Cosmetic changes:


- Map notes for BGEE quests
Games: BGEE, EET

Many BGEE quests require you to barge into an unmarked home in one of the game's cities to talk to the NPC there. And if you don't have what they need with you, you'll have to come back later. This component adds map notes for those homes, once you have a reason to go there - either you've been given the quest, or you have the quest item with you.
BGEE also has pre-placed map notes for some of these homes. This component removes those notes, then re-adds them after suitable unlock conditions.
For example, here's what the component does in Beregost:
- Landrin's house loses its marker. The marker comes back once you have either talked to Landrin or picked up an item she wants.
- Mirianne's house gains a marker once you either talk to her or pick up the scroll.
- Mr. Colquetle's house gets a marker once you pick up his son's amulet. (Talking to him without it doesn't give the quest, so you don't get the marker for it either.)

- Standardize tavern and inn music
Games: BGEE, EET

About 80% of the tavern and inn areas in the BGEE campaign follow a standard pattern for their area music; places where people eat and drink get tavern music, bedrooms have no music assigned. Those places don't actually have no music at all though; they inherit from the master area instead.
This component standardizes the remaining 20% of areas to follow this pattern.

BG2EE organizes area music a little differently, and has fewer inns. No changes are needed for that campaign.
SoD areas are also unchanged, as I don't have that expansion.

- Randomize battle music
Games: BGEE, BG2EE, EET

This component assigns randomly chosen battle music to all areas, including those that previously had no battle music assigned. The possible choices include all "songs" in base BGEE and BG2EE designed as battle music, plus anything used as battle music in existing areas that wasn't on the list already.
The random choice is made when this component is installed. Once installed, each area will have consistent battle music.

I had to do some pre-processing to remove unsuitable battle music from a number of areas in BGEE and BG2EE. This pre-processing has not been done with SoD, so that expansion may introduce unsuitable songs into the random pool.
EET games are also a major unknown for me, due to the way that battle music differs between BGEE and BG2EE. Not only do the songs have different IDS references, songs with the same name can be completely different. I don't think it'll add extra unsuitable songs into the pool, at least.

Changelog:

Version 2.1:
New component added:
- Nature's Beauty blindness can be cured

Version 2.0:
- Mac and Windows installers added
New components added:
- Map notes for BGEE quests
- Standardize tavern and inn music
- Randomize battle music
- Potion effects don't stack with themselves
- Bigger random spawns
Existing components updated:
- Vernus can be raised: ToB Bhaal power resurrection added to list of spells that work.
- Fix Black Pits oversights: Sandthief's Ring is now sold fully charged.
- Enchant Weapon works in contingencies: Bug fixed. Now properly deletes all existing rows of that 2DA.
- Shapeshift corrections: Shapeshift weapons now block the off hand in BGEE.
- Dueling fireshields don't go infinite: Now actually works in all games, not just BG2EE.
- Undead Hunters are better at Turn Undead: Description now uses the correct dash.
- Various components: tweaked code to improve performance or cover possible issues.
- Various components: added debug messages. The switch to enable/disable them is in jtweaks-ini.tph.

Version 1.1: Fixed an ordering error in the preamble. Should install now.