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
    ability_type=   "Target Point"
    affects=        "Enemy Units"
    damage_type=    "Instant Attack"
%}

Fire a round with deadly precision in the target direction, performing an instant attack with bonus damage on the first enemy unit it hits.
If the round encounters a tree, cliff, building, or firebomb (your E), it will ricochet, increasing the bonus damage each time it does so.
If the round ricochets at least once, it will also stun the victim.

- The round travels up to 1800 distance or until it hits a unit.
- Destroys trees it bounces on.
- The effect is instant (no visible projectile).

- Has 6 charges.  Charges do not recover over time.  You must use your (D) Reload ability to recover charges.
- Has a brief cast point and cooldown.

|**Bonus Damage per Bounce**|20/25/30/35
|**Max Bonus Damage**       |80/100/120/140
|**Attack Damage**          |40/50/60/70%
|**Stun Duration**          |0.4 seconds
|**Cast Point**             |0.4 seconds
|**Max Travel Distance**    |1800

|**Mana Cost**  |20             |**Max Charges**            |6
|**Cooldown**   |0.2 seconds    |**Charge Recovery Rate**   |N/A

{% include headers/hero_ability.html
    title=          "(D) Reload (SUB-ABILITY)"
    icon=           "assets/icons/reload-gun-barrel.png"
    ability_type=   "No Target"
    affects=        "Self"
%}

You can activate this ability and channel briefly to recover all bullet charges (6 max).
Any attack that consumes the first or last bullet charge will deal a guaranteed critical hit.

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

The Outlaw points out the target unit for a mugging, causing allied heroes to deal bonus damage and gain gold when they attack them.
If the victim is attacked a set number of times within the debuff duration, they become stunned and all nearby allies gain bonus gold.  The debuff is then dispelled.

- The Outlaw gains increased gold from the effect.
- The debuff duration is refreshed upon dealing damage.
- Only right-click attacks trigger the effect.
- This effect only grants gold, it does not actually steal gold from the victim.

|**Cast Range**                 |550
|**Bonus Damage**               |10/15/20/25
|**Ally Gold Steal per Attack** |2
|**Self Gold Steal per Attack** |6
|**Knockout Stack Threshold**   |8
|**Knockout Stun Threshold**    |0.3/0.8/1.3/1.8 seconds
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
%}

Toss a bundle of dynamite at the target point, which explodes after a short duration or when destroyed.
Enemies caught in the blast are knocked back, and take magic damage and a slowing DoT effect (effect decreases with distance from blast center).
The Outlaw is also knocked back if caught in the blast (doesn't affect allies otherwise).

Has a flat amount of HP, no magic resistance.
Can be attacked by allies but ally attacks always take 3 hits to kill, unless it is hit by Deadeye (Q), in which case it always explodes instantly.

- Deadeye can ricochet off the firebomb.
- The firebomb will never be attacked by creeps or towers (like ET sleep victims).

---
{% include headers/hero_ability.html
    title=          "(R) Witching Hour"
    icon=           "assets/icons/evil-moon.png"
    ability_type=   "No Target"
%}

The Outlaw mounts up and summons the gang for a mounted night raid.

On activation, it becomes night, the Outlaw gains haste, and a number of Night Riders are summoned: uncontrollable, fast-moving ranged units that follow and mimic the Outlaw.
When the Outlaw attacks a unit or casts Deadeye, his Night Riders will also attack or cast at the same unit or point.

- Witching Hour ends immediately if the Outlaw is killed (this is considered a transformation effect).
- Night Riders are targetable units and can be killed by enemies.
- Night Riders have flying movement and will follow the Outlaw, circling him randomly when they catch up.
- Night Riders have fixed stats and don't scale with items.
- Night Riders have a random, short delay before they mimic the Outlaw, and don't mimic it at exactly the same point.
- Night Riders do not require charges to use Deadeye.
- The Night Riders will vanish immediately when Witching Hour ends (for any reason).

|**Night Riders Summoned**  |1/2/3
|**Haste Speed**            |550
|**Duration**               |18 seconds

|**Mana Cost**  |150/200/250
|**Cooldown**   |100/90/80 seconds

---
## Scepter Upgrade
Improved Witching Hour

- Night Riders now also mimic Ace in the Hole (E), throwing firebombs near the same point the Outlaw does with a random short delay.
- Increases duration by 4 seconds.

---
## Shard Upgrade
Improved Reload

- Can now move at 50% speed while reloading (like CM shard).
- Decreases Reload cooldown by 10.

---
## Talents

|10|    +1.5 Mana Regen                 | +4 Stickup Gold Steal
|15|    +100 Attack Range               | Ace in the Hole applies Disarm
|20|    +80% Reload Guaranteed Crit     | 400 AoE Stickup
|25|    +1 Witching Hour Night Rider    | 2 Charges Ace in the Hole
