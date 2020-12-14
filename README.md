# SKAL

### Donate
> https://www.buymeacoffee.com/Lede


### Youtube
> https://www.youtube.com/channel/UCgwJYHQsbW_cPWfOFXo0XXQ


### Discord
> https://discord.gg/ZZc7fBK

# Contents
### Events
- 
<span color="red">red</span>
### Conditions
#### > Ver 1.0.0
- [Holding sword](#Holding-sword)
- [Holding pickaxe](#Holding-pickaxe)
- [Holding axe](#Holding-axe)
- [Holding shovel](#Holding-shovel)
- [holding hoe](#Holding-hoe)
- [isCoolSet](#isCoolSet)

### Effects
##### > Ver 1.0.0
- [Give](#Give)

### Expressions
##### > Ver 1.0.0
- [Display name](#Display-name)
- [Tab name](#Tab-name)
- [Cooltime](#Cooltime)
- [Holding click](#Holding-click)

### Types
-


# Events

# Conditions

## > Ver 1.0.0

### Holding Sword

> Syntax
```
%livingentity% (1¦(held|hold)|2¦(n[ot][ ]held|n[ot][ ]hold)) sword
```
> Description
```
Check if the item that the player and entity are holding on the main hand is the sword.
Detects DIAMOND_SWORD, GOLD_SWORD, IRON_SWORD, STONE_SWORD, and WOOD_SWORD.

플레이어및 엔티티가 메인핸드에 들고있는 아이템이 검인지 체크합니다.
DIAMOND_SWORD, GOLD_SWORD, IRON_SWORD, STONE_SWORD, WOOD_SWORD 를 감지합니다.
```
> Example
```
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

플레이어및 엔티티가 메인핸드에 들고있는 아이템이 곡괭이인지 체크합니다.
DIAMOND_PICKAXE, GOLD_PICKAXE, IRON_PICKAXE, STONE_PICKAXE, WOOD_PICKAXE 를 감지합니다.

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

플레이어및 엔티티가 메인핸드에 들고있는 아이템이 도끼인지 체크합니다.
DIAMOND_AXE, GOLD_AXE, IRON_AXE, STONE_AXE, WOOD_AXE 를 감지합니다.

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

플레이어및 엔티티가 메인핸드에 들고있는 아이템이 삽인지 체크합니다.
DIAMOND_SPADE, GOLD_SPADE, IRON_SPADE, STONE_SPADE, WOOD_SPADE 를 감지합니다.

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

플레이어및 엔티티가 메인핸드에 들고있는 아이템이 낫인지 체크합니다.
DIAMOND_HOE, GOLD_HOE, IRON_HOE, STONE_HOE, WOOD_HOE 를 감지합니다.

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

- 설명
String을 이름으로 갖는 쿨타임이 남아있는지 체크합니다.

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

무기, 방어구, 도구, 포션 등 겹쳐지지 않는 아이템들을 겹친 상태로 플레이어에게 지급합니다.

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

플레이어의 디스플레이 이름을 가져옵니다

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

플레이어의 탭리스트 이름을 가져옵니다

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

String 이름을 갖는 쿨타임을 생성합니다.
쿨타임은 저장되지 않습니다. 플러그인 리로드시 초기화됩니다

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

우클릭 유지시 유지 시간을 확인합니다.
on Click 이벤트에서 작동합니다.
4tick 단위로 체크합니다.

- Example
on right click:
    if hold time of player > 100:
        send "Charging complete"
    
on right click:
    send "%htime of player%"
```

# Types

























