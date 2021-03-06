# Weapons Data
This section contains data about weapons Samus can use in Super Metroid.
Weapons here not necessarily items, but can be any number of different ways enemies can be attacked.
Currently, beam combos and special beam attacks are not represented as weapons because they are not believed to have any logical relevance.

## Folder Structure
This folder simply contains the [main.json](main.json) file, which contains data about all weapons.

## Contents of a Weapons File
The weapons file follows the schema defined at [/schema/m3-weapons.schema.json](../schema/m3-weapons.schema.json).

The file contains an array of Weapons, and includes data about its damage and requirements.

### name
The name by which this weapon will be referenced in other files.

### damage
The damage this weapon inflicts on an enemy with no multipliers and no invulnerabilities for it.

### useRequires
A list of [logical requirements](../logicalRequirements.md) that must be met before being able to use the weapon.

### shotRequires
A list of [logical requirements](../logicalRequirements.md) that must be met (on top of the use requirements) for each shot of this weapon that Samus fires. This will generally be an ammo cost.

### situational
A boolean that indicates whether the weapon should be considered situational. Weapons that are situational cannot be assumed to be generally usable, as they tend to require a specific setup, circumstance, or need. Because of this, situational weapons will not fulfill an `enemyKill` logical element, unless referenced explicitly.

### hitsGroup
A boolean that indicates whether the weapon is able to hit all enemies in a group with one shot. Because the number of shots required is only relevant for weapons that have a cost per shot, weapons with unlimited use will likely always have a value of `false` for this property.

### categories
A list of categories that the weapon is a part of. Categories are used in the [enemies files](../enemies/enemies-readme.md) to reference sets of weapons at once when defining damage multipliers and invulnerabilities. Categories include:
* _All:_ A category which all weapons are part of. Used for fully invulnerable enemies.
* _Beam_: A category which includes all beam attacks, including charged shots
* _UnchargedBeam_: A category which includes all beam attacks, but not charged shots
* _PowerBombBlast:_ Power Bombs have been split into two weapons because the central area hits twice and the periphery hits once. This category groups both.
