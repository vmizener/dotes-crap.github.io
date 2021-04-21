---
layout: default

title: Varret, Outlaw
attribute: Agility
attack_type: Ranged

---
{% capture anchor %}{{ site.baseurl }}{{ page.url }}{% endcapture %}

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
| **Damage** (at Level 1)       | 53 - 61 |
| **Attack Type**               | {{ page.attack_type }} |
| **Attack Range**              | 600 |
| **Projectile Speed**          | 1200 |

| :- | :- | :- | :- |
| **Strength**      | 18 + 2.2  | **Health Regen**       | 0.0 |
| **Agility**       | 24 + 2.9  | **BAT**                | 1.9 |
| **Intelligence**  | 20 + 1.8  | **Armor** (at Level 1) | 2.0 |

| **Health** (at Level 1)   | {{ 18 | times: 20 | plus: 200 }}
| **Mana** (at Level 1)     | {{ 20 | times: 12 | plus: 75 }}

---
## Abilities

{% include headers/hero_ability.html
    title=          "(Q) Deadeye"
    icon=           "assets/icons/dead-eye.png"
    ability_type=   "Target Point"
    affects=        "Enemy Units"
    damage_type=    "Instant Attack"
%}


Fire a round from your trusty revolver at the target point, which then bounces and strikes the nearest enemy unit from that point.
The round performs an instant attack and knocks back the first enemy unit it hits, doing additional bonus damage and stunning if it managed to bounce first.

- The round travels up to a total of 900 distance or until it hits a unit.
- The effect is instant (no visible projectile).
- If the round hits a tree, the tree is destroyed and no damage is dealt.
- Has 6 charges.  Charges do not recover over time.  You must use your [Reload]({{anchor}}#d-reload) sub-ability to recover charges.
- Has a minimum cast range of 300.
- Ignores structures.
- Ignores spell immunity.

|**Minimum Cast Range**     |300
|**Maximum Cast Range**     |900
|**Max Travel Distance**    |900
|**Attack Damage**          |55/65/75/85%
|**Knockback Distance**     |50
|**Bounce Bonus Damage**    |15/30/45/60
|**Bounce Stun Duration**   |0.25 seconds
|**Cast Point**             |0.2 seconds

|**Mana Cost**  |20           |**Max Charges**            |6
|**Cooldown**   |2 seconds    |**Charge Recovery Rate**   |N/A

{% include headers/hero_ability.html
    title=          "(D) Reload"
    icon=           "assets/icons/reload-gun-barrel.png"
    ability_type=   "No Target"
    affects=        "Self"
%}

You can activate this ability and channel briefly to recover all [Deadeye]({{anchor}}#q-deadeye) charges (6 max).

- An attack that consumes the first or last bullet charge will deal a guaranteed critical hit.
- You can move at reduced speed and use items/abilities while reloading (like CM shard).
- [Deadeye]({{anchor}}#q-deadeye) and [Fan the Hammer]({{anchor}}#f-fan-the-hammer) are disabled while reloading.

|**First/Last Round Critical**  |180%
|**Movement Speed Penalty**     |40%
|**Channel Time**               |2 seconds

|**Mana Cost**  |0
|**Cooldown**   |26 seconds

---
{% include headers/hero_ability.html
    title=          "(W) Stickup"
    icon=           "assets/icons/bandit.png"
    ability_type=   "Target Unit"
    affects=        "Enemy Heroes"
%}

Point out the target unit for a mugging, causing allied heroes to deal bonus damage and gain gold when they attack them.
If the victim is attacked a set number of times within the debuff duration, they become stunned, slowed, and all nearby allies gain bonus gold.  The debuff is then dispelled.

- The Outlaw gains increased gold from the effect.
- The debuff duration is refreshed upon dealing damage.
- Only right-click attacks trigger the effect.
- The knockout bonus gold only grants gold; only the triggering attacks actually steal gold from the victim.

|**Cast Range**                 |550
|**Bonus Damage**               |10/17/24/31
|**Ally Gold Steal per Attack** |2
|**Self Gold Steal per Attack** |6
|**Knockout Stack Threshold**   |8
|**Knockout Movement Slow**     |35%
|**Knockout Slow Duration**     |3 seconds
|**Knockout Stun Duration**     |0.3/0.8/1.3/1.8 seconds
|**Ally AOE Gold on Knockout**  |16
|**Self AOE Gold on Knockout**  |40
|**Debuff Duration**            |2 seconds

|**Mana Cost**  |40/45/50/55
|**Cooldown**   |13 seconds

---
{% include headers/hero_ability.html
    title=          "(E) Ace in the Hole"
    icon=           "assets/icons/dynamite.png"
    ability_type=   "Target Point"
    affects=        "Enemy Units"
    damage_type=    "Magical"
%}

Toss a bundle of dynamite at the target point, which explodes after a short duration or when destroyed.
Enemies caught in the blast are knocked back, and take magic damage and a slowing DoT effect.

- The firebomb is considered a unit (not a ward).
- The firebomb can be attacked by allies and is affected by spells.
- If destroyed, there is a 0.5 second delay before the blast occurs.
- [Deadeye]({{anchor}}#q-deadeye) deals double damage to the firebomb.
- The firebomb will never be attacked by creeps or towers (like ET sleep victims).
- The firebomb is initially invulnerable to damage before becoming active.
- The explosion deals full damage to close units and half damage to farther ones.
- Destroys trees in the blast area.

|**Cast Range**                 |500
|**Activation Delay**           |1.5 seconds
|**Explosion Delay**            |5.0 seconds
|**Destruction Delay**          |0.5 seconds
|**Firebomb Health**            |175/225/275/325
|**Firebomb Armor**             |0
|**Firebomb Magic Resistance**  |0
|**Blast Damage**               |105/210/315/420
|**Full Blast Damage Radius**   |200
|**Half Blast Damage Radius**   |375
|**Burn Damage**                |20
|**Burn Movement Slow**         |15/20/25/30%
|**Burn Duration**              |3 seconds
|**Knockback Range**            |350

|**Mana Cost**  |65/90/115/140
|**Cooldown**   |47/43/39/35 seconds

---
{% include headers/hero_ability.html
    title=          "(R) Witching Hour"
    icon=           "assets/icons/evil-moon.png"
    ability_type=   "No Target"
%}

The Outlaw mounts up and summons the gang for a mounted night raid.

On activation, it becomes night, the Outlaw gains haste, and a number of Night Riders are summoned: uncontrollable, fast-moving ranged units that follow and mimic the Outlaw.
When the Outlaw attacks a unit or casts an ability other than [Ace in the Hole]({{anchor}}#e-ace-in-the-hole), his Night Riders will also attack or cast at the same unit or point.
In addition, the duration of Witching Hour is paused while near enemy heroes, up to a maximum duration.

- Witching Hour ends immediately if the Outlaw is killed (this is considered a transformation effect).
- Night Riders are targetable units and can be killed by enemies.
- Night Riders have flying movement and will follow the Outlaw, circling him randomly when they catch up.
- Night Riders deal a percentage of the Outlaw's damage, but otherwise have fixed stats and do not scale with items.
- Night Riders have a random, short delay before they mimic the Outlaw, and don't mimic it at exactly the same point.
- Night Riders do not require charges to use [Deadeye]({{anchor}}#q-deadeye) or [Fan the Hammer]({{anchor}}#f-fan-the-hammer), though they will still mimic [Reload]({{anchor}}#d-reload) when you cast it.
- The Night Riders will vanish immediately when Witching Hour ends (for any reason).
- Witching Hour does not end prematurely when losing all of your Night Riders (you maintain your movement speed bonus and it remains night).

|**Transformation Delay**   |1.2 seconds
|**Night Riders Summoned**  |3
|**Night Rider Health**     |1200/1800/2400
|**Night Rider Damage**     |35/50/65%
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
- Causes Night Riders to also mimic [Ace in the Hole]({{anchor}}#e-ace-in-the-hole), throwing firebombs near the same point the Outlaw does with a random short delay.

---
## Shard Upgrade
New Ability:

{% include headers/hero_ability.html
    title=          "(F) Fan the Hammer"
    icon=           "assets/icons/gunshot.png"
    ability_type=   "Target Point"
    affects=        "Enemy Units"
    damage_type=    "Instant Attack"
%}

Rapidly fire all charges of [Deadeye]({{anchor}}#q-deadeye) at the target point, then instantly reload.

- There is a slight delay between attacks.
- The shots are fired at a random offset close to the target point.

|**Attack Delay**       |0.16 seconds
|**Min Target Offset**  |0
|**Max Target Offset**  |50

|**Mana Cost**  |100
|**Cooldown**   |30 seconds

---
## Talents

|10| +1.5 Mana Regen | +4 [Stickup]({{anchor}}#w-stickup) Gold Steal
|15| +125 Attack Range | -8 [Ace in the Hole]({{anchor}}#e-ace-in-the-hole) Cooldown
|20| +80% [Reload]({{anchor}}#d-reload) Guaranteed Crit | Attack [Stickup]({{anchor}}#w-stickup) Target While Moving
|25| [Night Rider]({{anchor}}#r-witching-hour) Magic Immunity | 400 AoE [Stickup]({{anchor}}#w-stickup)
