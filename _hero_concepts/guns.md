---
layout: default

title: Varret, Outlaw
attribute: Agility
attack_type: Ranged

---

# {{ page.title }}
{{ page.attack_type }} {{ page.attribute }} Hero

---
## Lore
asdf

## Appearance
asdf

---
## Stats

| **Primary Attribute**         | {{ page.attribute }} |
| **Movement Speed**            | 285 |
| **Base Damage** (at Level 1)  | 55 - 61 |
| **Attack Type**               | {{ page.attack_type }} |
| **Attack Range**              | 600 |
| **Projectile Speed**          | 1200 |

| :- | :- | :- | :- |
| **Strength**      | 18 + 2.2  | **Health Regen**       | 0.0 |
| **Agility**       | 24 + 2.9  | **BAT**                | 1.9 |
| **Intelligence**  | 20 + 1.8  | **Armor** (at Level 1) | 2.0 |

---
## Abilities

{% include headers/hero_ability.html
    title=          "(Q) Deadeye"
    icon=           "assets/icons/dead-eye.png"
    ability_type=   "Vector Target"
    affects=        "Enemy Units"
    damage_type=    "Instant Attack"
%}

Fire a round from your trusty revolver at the target point, which then bounces and travels in the vector-targeted direction.
The round performs an instant attack with bonus damage on the first enemy unit it hits, additionally stunning if it managed to bounce first.

- The round travels up to a total of 1800 distance or until it hits a unit.
- The effect is instant (no visible projectile).
- If the round hits a tree, the tree is destroyed and no damage is dealt.
- Has 6 charges.  Charges do not recover over time.  You must use your (D) Reload ability to recover charges.
- Has a minimum cast range of 400.

|**Minimum Cast Range**     |400
|**Maximum Cast Range**     |1800
|**Max Travel Distance**    |1800
|**Bonus Damage**           |20/40/60/80
|**Attack Damage**          |70%
|**Stun Duration**          |0.4 seconds
|**Cast Point**             |0.4 seconds

|**Mana Cost**  |15             |**Max Charges**            |6
|**Cooldown**   |1.2 seconds    |**Charge Recovery Rate**   |N/A

{% include headers/hero_ability.html
    title=          "(D) Reload (SUB-ABILITY)"
    icon=           "assets/icons/reload-gun-barrel.png"
    ability_type=   "No Target"
    affects=        "Self"
%}

You can activate this ability and channel briefly to recover all Deadeye charges (6 max).
An attack that consumes the first or last bullet charge will deal a guaranteed critical hit.

|**First/Last Round Critical**  |180%
|**Channel Time**               |3.0 seconds

|**Mana Cost**  |100
|**Cooldown**   |28/24/20/16 seconds

---
{% include headers/hero_ability.html
    title=          "(W) Stickup"
    icon=           "assets/icons/bandit.png"
    ability_type=   "Target Hero"
    affects=        "Enemies"
%}

Point out the target unit for a mugging, causing allied heroes to deal bonus damage and gain gold when they attack them.
If the victim is attacked a set number of times within the debuff duration, they become stunned, slowed, and all nearby allies gain bonus gold.  The debuff is then dispelled.

- The Outlaw gains increased gold from the effect.
- The debuff duration is refreshed upon dealing damage.
- Only right-click attacks trigger the effect.
- The knockout bonus gold only grants gold; only the triggering attacks actually steal gold from the victim.

|**Cast Range**                 |550
|**Bonus Damage**               |10/15/20/25
|**Ally Gold Steal per Attack** |2
|**Self Gold Steal per Attack** |6
|**Knockout Stack Threshold**   |8
|**Knockout Stun Duration**     |0.3/0.8/1.3/1.8 seconds
|**Knockout Slow Duration**     |0.9/1.6/2.3/3.0 seconds
|**Knockout Movement Slow**     |35%
|**Ally AOE Gold on Knockout**  |16
|**Self AOE Gold on Knockout**  |40
|**Debuff Duration**            |2 seconds

|**Mana Cost**  |20/25/30/35
|**Cooldown**   |13/11/9/7 seconds

---
{% include headers/hero_ability.html
    title=          "(E) Ace in the Hole"
    icon=           "assets/icons/dynamite.png"
    ability_type=   "Target Point"
    affects=        "Enemies"
    damage_type=    "Magical"
%}

Toss a bundle of dynamite at the target point, which explodes after a short duration or when destroyed.
Enemies caught in the blast are knocked back, and take magic damage and a slowing DoT effect.

- The firebomb is considered a unit (not a ward).
- The firebomb can be attacked by allies and is affected by spells.
- Deadeye (Q) can directly target the firebomb to deal damage to it in addition to ricocheting off it.
- The firebomb will never be attacked by creeps or towers (like ET sleep victims).
- The firebomb is invulnerable to damage for the first second upon being created.
- Destroys trees in the blast area.

|**Cast Range**                 |700
|**Activation Delay**           |1 second
|**Explosion Delay**            |5 seconds
|**Firebomb Health**            |175/200/225/250
|**Firebomb Armor**             |0
|**Firebomb Magic Resistance**  |0
|**Blast Damage**               |75/180/285/390
|**Full Blast Damage Radius**   |175
|**Half Blast Damage Radius**   |350
|**Burn Damage**                |20
|**Burn Movement Slow**         |15/20/25/30%
|**Burn Duration**              |3 seconds
|**Knockback Range**            |350

|**Mana Cost**  |95/130/165/200
|**Cooldown**   |45/41/37/33 seconds

---
{% include headers/hero_ability.html
    title=          "(R) Witching Hour"
    icon=           "assets/icons/evil-moon.png"
    ability_type=   "No Target"
%}

The Outlaw mounts up and summons the gang for a mounted night raid.

On activation, it becomes night, the Outlaw gains haste, and a number of Night Riders are summoned: uncontrollable, fast-moving ranged units that follow and mimic the Outlaw.
When the Outlaw attacks a unit or casts Deadeye, his Night Riders will also attack or cast at the same unit or point.
In addition, the duration of Witching Hour is paused while near enemy heroes, up to a maximum duration.

- Witching Hour ends immediately if the Outlaw is killed (this is considered a transformation effect).
- Night Riders are targetable units and can be killed by enemies.
- Night Riders have flying movement and will follow the Outlaw, circling him randomly when they catch up.
- Night Riders have fixed stats and don't scale with items.
- Night Riders have a random, short delay before they mimic the Outlaw, and don't mimic it at exactly the same point.
- Night Riders do not require charges to use Deadeye.
- The Night Riders will vanish immediately when Witching Hour ends (for any reason).
- Witching Hour does not end prematurely when losing all of your Night Riders.

|**Transformation Delay**   |1.2 seconds
|**Night Riders Summoned**  |3
|**Night Rider Health**     |1200/1800/2400
|**Night Rider Base Damage**|45/80/115
|**Haste Speed**            |550
|**Nearby Enemy Radius**    |450
|**Min Duration**           |6 seconds
|**Max Duration**           |18 seconds

|**Mana Cost**  |150/200/250
|**Cooldown**   |120/100/80 seconds

---
## Scepter Upgrade
Improved Witching Hour

- Increases min/max duration by 4 seconds.
- Increases Night Rider health by 600.
- Causes Night Riders to also mimic Ace in the Hole (E), throwing firebombs near the same point the Outlaw does with a random short delay.

---
## Shard Upgrade
Improved Reload

- Can now move at 75% speed while reloading.
- Removes Reload cooldown.

---
## Talents

|10| +1.5 Mana Regen                | +4 Stickup Gold Steal
|15| +125 Attack Range              | Attack Stickup Target While Moving
|20| +80% Reload Guaranteed Crit    | 2 Charges Ace in the Hole
|25| Night Rider Magic Immunity     | 400 AoE Stickup
