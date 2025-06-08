

Choices
Upgrade/NonUpgrade

- Let's stick with switching out weapons (so non upgradeable)
- Have enchantments (subtypes of the same weapon)
- Have a tier/rarity system (the deeper you go the less you see the "beginner" weapons and more you see the "advanced" weapons)


- Weapon has base damage range
- Adjustable by Character stats

# Weapon variables
- Min/Max Damage
- Durability : As weapon gets "weaker" deals less damage : Breaks at 0
- Quality (Probably won't use this) 
- Enchantment/s (Effects? Enchantment Class)
    - Passive Buffs
    - Activated Buff - Use the weapon as an item
    - On hit - You smack someone
- Range
- Ammo Requirement (For other needed items/weapons - Throwable weapons will be special items?)


-----------Base Items Config file--------
id name min max durab qual range ammoreq itemtypes
0  longsword 3 7                            1

-----------Different Enchantments file
id name ----------------------

------------BaseWeaponEnchantments----------
baseid     enchid
0            3
0            5

-----------Posssible Enchantments----------
enchanttypes          enchid
1                       1
1                       2
1                       3
1                       5

