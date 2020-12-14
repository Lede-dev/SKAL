# Contents
### Events
- 

### Conditions
#### > Ver 1.0.0
- Holding sword
- Holding pickaxe
- Holding axe
- Holding shovel
- holding hoe
- isCoolSet

### Effects
##### > Ver 1.0.0
- Give

### Expressions
##### > Ver 1.0.0
- Display name
- Tab name
- Cooltime
- Holding click

### Types
-


# Events

# Conditions

## > Ver 1.0.0

### Holding Sword
```
- Syntax
%livingentity% (1¦(held|hold)|2¦(n[ot][ ]held|n[ot][ ]hold)) sword

- Description
Check if the item that the player and entity are holding on the main hand is the sword.
Detects DIAMOND_SWORD, GOLD_SWORD, IRON_SWORD, STONE_SWORD, and WOOD_SWORD.

- Example
command /test:
    trigger:
        if player held sword:
            send "Held Sword"
        else if player not held sword:
            send "Not Held Sword"
```

### Holding pickaxe
```
- Syntax
%livingentity% (1¦(held|hold)|2¦(n[ot][ ]held|n[ot][ ]hold)) pickaxe

- Description
Check if the item that the player and entity are holding on the main hand is a pickaxe.
Detects DIAMOND_PICKAXE, GOLD_PICKAXE, IRON_PICKAXE, STONE_PICKAXE, WOOD_PICKAXE.

- Example
command /test:
    trigger:
        if player held pickaxe:
            send "Held Pickaxe"
        else if player not held pickaxe:
            send "Not Held Pickaxe"
```

### Holding axe
```
- Syntax
%livingentity% (1¦(held|hold)|2¦(n[ot][ ]held|n[ot][ ]hold)) axe

- Description
Check if the item that the player and entity are holding on the main hand is an ax.
Detects DIAMOND_AXE, GOLD_AXE, IRON_AXE, STONE_AXE, and WOOD_AXE.

- Example
command /test:
    trigger:
        if player held axe:
            send "Held Axe"
        else if player not held axe:
            send "Not Held Axe"
```

### Holding shovel
```
- Syntax
%livingentity% (1¦(held|hold)|2¦(n[ot][ ]held|n[ot][ ]hold)) (shovel|spade)

- Description
Check if the item that the player and entity are holding on the main hand is a shovel.
Detects DIAMOND_SPADE, GOLD_SPADE, IRON_SPADE, STONE_SPADE, WOOD_SPADE.

- Example
command /test:
    trigger:
        if player held shovel:
            send "Held Shovel"
        else if player not held shovel:
            send "Not Held Shovel"
```

### Holding hoe
```
 [ HeldHoe ]

- Syntax
%livingentity% (1¦(held|hold)|2¦(n[ot][ ]held|n[ot][ ]hold)) hoe

- Description
Check if the item that the player and entity are holding on the main hand is better.
Detects DIAMOND_HOE, GOLD_HOE, IRON_HOE, STONE_HOE, and WOOD_HOE.

- Example
command /test:
    trigger:
        if player held hoe:
            send "Held Hoe"
        else if player not held hoe:
            send "Not Held Hoe"
```

### isCoolSet
```
 [ isCoolSet ]

- Syntax
r[emain][ ]cool %string%

- Description
Check if there is still a cool time left to have String by name.

- Example
command /test [<string>]:
    trigger:
        if remain cool arg 1:
            send "%cool arg 1%"
            
command /test:
    set {_name} to "test":
        if rcool {_name}:
            send "%cool {_name}%"
```

# Effects

## > Ver 1.0.0

### Give
```
- Syntax
[s][kal][ ]give %itemstack% to %player%

- Description
Non-overlapping items such as weapons, armor, tools, and potion will be give in overlapping states.

- Example
command /test:
    trigger:
        set {_item} to stone sword named "&eTEST"
        skal give {_item} to player
        
command /test:
    trigger:
        set {_item} to stone sword named "&dTEST2"
        sgive {_item} to player
```

# Expressions

## > Ver 1.0.0

### Display name
```
 [ Display name ]

- Syntax
[the] d[isplay][ ]name of %player%

- Description
Gets the player's display name

- Example
command /dname:
    broadcast dname of player
    
command /setDname [<string>]:
    set dname of player to arg 1
    
command /resetDname:
    delete dname of player
    reset dname of player
```

### Tab name
```

- Syntax
[the] t[ab][ ]name of %player%

- Description
Gets the name of the player's tab list

- Example
command /tname:
    broadcast tname of player
    
command /setTname [<string>]:
    set tname of player to arg 1
    
command /resetTname:
    delete tname of player
    reset tname of player
```

### Cooltime
```
- Syntax
[the] cool[time] %string%

- Description
Create a cool time with a name for String.
Cool Time is not saved. Initialized on plugin reload

- Example
command /setCool [<string>] [<number>]:
    set cool arg 1 to arg 2
    broadcast "%cool arg 1%"
    
command /getCool [<string>]:
    set {_cool} to cool arg 1
    broadcast "%{_cool}%"
    
command /delCool [<string>]:
    delete cool arg 1
    broadcast "%cool arg 1%"
    
command /addCool [<string>] [<number>]:
    add arg 2 to cool arg 1
    broadcast "%cool arg 1%"
    
command /remCool [<string>] [<number>]:
    remove arg 2 from cool arg 1
    boradcast "%cool arg 1%"
    
on Damage:
    if attacker is player:
        set {_name} to "Attack_Delay_%uuid of attacker%"
        if remain cool {_name}:
            cancel event
            stop
        set cool {_name} to 40 #40 ticks
```

### Holding click
```
- Syntax
[the] h[old][ing][ ]time of %player%

- Description
Check the right click hold time.
Used in on click event
Check every 4tick.

- Example
on right click:
    if hold time of player > 100:
        send "Charging complete"
    
on right click:
    send "%htime of player%"
```

# Types

























