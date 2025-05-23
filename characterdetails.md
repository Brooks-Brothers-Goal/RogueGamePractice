# Attributes
- Hp : Max HP - INTEGERS
- Mana : Max Mana - INTEGERS
- name : string
- Strength : INTEGER 
    - Melee Damage Bonus
- Dexterity : INTEGER
    - Range Damage Bonus
- Dodge : FLOAT
    - Percent 0-100.00 chance that dodges it 
-  SightRange : INTEGER
    - In squares
- Noise : INTEGER
    - A way to attract opponents/Can Hear Opponents?
- Listen : INTEGER
    - How far away can character hear? I was thinking that if a character listen and opponents noise is bigger than distance some way to know
- Inventory : List of <ITEM>
    - All Items should probably be a base class with certain pieces of information?
- Equipped : Dictionary with <SLOT : ITEM>
    - Slot will be an ENUM of specific values 
- Level : INT
- KnownAbilitiies : List of <ABILITIES>
- CurrentEffects : Dict of <TAG : EFFECT>
    - There can only be one of each tag - need to probably have effects define what to do if already exists
    - The tags should be uniquely made if they are generic, but able to find it
    - Iterating through them will be used with the keys
- Accuracy : FLOAT
    - Percent between 0-100.00, Thinking the chance of hit will be Target Dodge - Attacker Accuracy : Then random number generated if over the result it's a HIT
- Defence : INTEGER
    - How much to reduce the Damage from an attack by
- Race : ENUM(RACE)
    - Must be a valid value from a Race ENUM defined somehow
- Class : ENUM(CLASS)
    - Must be a valid value from a Class ENUM defined somehow - probably in config files
- Position : COORD(X, Y, Floor?)
    - From a position Class for some helpful functions (unless one is found)
- Speed : INTEGER
    - For how fast can move/when they take turns in order
- XP : INTEGER
    -Gained XP
- Some way to hook in a player controller... Maybe a bool
    - For Now PlayerControlled : BOOL 
        - So that an effect can change this for a time - and in the main game logic, it checks if it's a player or not

# Useful Functions 
- GetEffectiveAttribute(attribute: string?)->INT/FLOAT/
    - probably need a way to define what attributes this can be used on
    - Simple list would be these I think? - This may get the weapons modification as well?
        - Strength
        - Dexterity
        - Accuracy
        - Mana/Max Mana
        - Hp/Max Hp
        - Dodge
        - SightRange
        - Noise
        - Listen
        - Defence
        - Speed
        - Player Controlled?
    - Will take the base value, apply any applicable effects
- GetIsAware(Opponent:Character)-><SEEN/HEARD/BOTH/NEITHER> 
    - If can see opponent or hear them then they are "aware"
    - Uses active values of Noise, Listen and SightRange
    - Checks that nothing is blocking
    - May need to make some way to have walls/tiles affect both sight range and sound
    - Sound will probably need to be closest path not through walls
- GetHasEffect(EffectTag: String?)->Bool
    - If the tag exists or not
- TakeDamage(Damage: Damage)
    - Apply the Damage

# Still need to do
[ ] Plan out how Classes strengthen them...
[ ] Slot ENUM
[ ] EFFECT Class
[ ] COORD Class
[ ] Abilities Class
[ ] Sequence Diagram for 
    [ ] Preforming an action (Attack/Move/ETC)
[ ] How to add component system?