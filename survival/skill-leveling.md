# Skill Leveling

Every Player on the server has **skills**, that can be leveled up by performing certain actions. In addition there are Stats that are improved by leveling **stats**.
Your skills can be viewed by using the command **/skills**.

{% hint style="warning" %}
> 1.21.5 heavily broke our previous skills system, and I decided to recode it from scratch so it was 100% our code without relying on 3rd party dependencies, as it would be easier than fixing the old, outdated code base and better for future feature integration
Feel free to follow our progress in development of the skill system on our [**Discord**](../general/discord.md)!\

So far Stats and Skills have been fully added back, with the exception of Skill Abilities. We are working to implement them over the coming weeks!
{% endhint %}

---

## Stats

- **Agility**
     - Increases base movement speed
- **Wisdom**
     - Improves Skill XP absorbance
     - Improves Vanilla XP absorbance
- **Defense**
     - Increases damage resistance
- **Vigor**
     - Increases attack damage

---

## Skills

- **Mining**
    - EXP is gained by **breaking blocks**
    - Abilities:
        - Sharpened Picks
        - Cave Adrenaline
        - Ore Mastery
    - Improves Stats:
        - Wisdom
        - Agility
- **Armory**
    - EXP is gained by **taking damage** in combat
    - Abilities:
        - Shamanism
        - Infernal Resistance
        - Bravery
    - Improves Stats:
        - Defense
        - Vigor      
- **Combat**
    - EXP is gained by **killing** naturally spawned mobs
    - Abilities:
        - Serrated Strikes
        - Dazzle
        - Fury
    - Improves Stats:
        - Vigor
        - Defense
- **Farming**
    - EXP is gained by harvesting crops and breeding animals
    - Abilities:
        - Satiation
        - Farmers Fortune
    - Improves Stats:
        - Wisdom
        - Agility
- **Woodcutting**
    - EXP is gained by **cutting down trees**
    - Abilities:
        - Axe Smithing
        - Lumberjack Mastery
    - Improves Stats:
        - Wisdom
        - Vigor
- **Exploration**
    - EXP is gained by **moving** through the world
    - Abilities:
        - Seamless Movement
        - Dodging
        - Adrenaline Channeling
    - Improves Stats:
        - Agility
        - Wisdom
- **Fishing**
    - EXP is gained by **fishing**
    - Abilities:
        - Bait Efficiency
        - Eye of the Depths
    - Improves Stats:
        - Agility
        - Wisdom
- **Alchemy**
    - EXP is gained by **brewing** potions
    - Abilities:
        - Efficient Brewing
        - Potionmaster
        - Mystic Resilience
    - Improves Stats:
        - Defense
        - Agility
- **Enchanting**
    - EXP is gained by **enchanting** items and upgrading enchantments
    - Abilities:
        - Lapis Efficiency
        - Glyph Mastery
        - Tool Rebirth
    - Improves Stats:
        - Wisdom
        - Defense
