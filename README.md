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

##### > Ver 1.0.1
- [Fill](#Fill)
- [Fill all](#Fill-all)
- [Fill slot](#Fill-slot)
- [Fill all slot](#Fill-all-slot)

##### > Ver 1.1.0
- [Knockback](#Knockback)
- [Grab](#Grab)

##### > Ver 1.2.0
- [Glowing](#Glowing) !! Required [GlowAPI](https://www.spigotmc.org/resources/api-glowapi.19422/), [PacketListenerAPI](https://www.spigotmc.org/resources/api-packetlistenerapi.2930/) !!

### Expressions
##### > Ver 1.0.0
- [Display name](#Display-name)
- [Tab name](#Tab-name)
- [Cooltime](#Cooltime)
- [Holding click](#Holding-click)

##### > Ver 1.1.0
- [Attack speed](#Attack-speed)
- [Attack damage](#Attack-damage)

### Types
-


# Events

# Conditions

## > Ver 1.0.0

- ### Holding Sword

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

- ### Holding pickaxe

> Syntax
```
%livingentity% (1¦(held|hold)|2¦(n[ot][ ]held|n[ot][ ]hold)) pickaxe
```
> Description
```
Check if the item that the player and entity are holding on the main hand is a pickaxe.
Detects DIAMOND_PICKAXE, GOLD_PICKAXE, IRON_PICKAXE, STONE_PICKAXE, WOOD_PICKAXE.

플레이어및 엔티티가 메인핸드에 들고있는 아이템이 곡괭이인지 체크합니다.
DIAMOND_PICKAXE, GOLD_PICKAXE, IRON_PICKAXE, STONE_PICKAXE, WOOD_PICKAXE 를 감지합니다.
```
> Example
```
command /test:
    trigger:
        if player held pickaxe:
            send "Held Pickaxe"
        else if player not held pickaxe:
            send "Not Held Pickaxe"
```

- ### Holding axe

> Syntax
```
%livingentity% (1¦(held|hold)|2¦(n[ot][ ]held|n[ot][ ]hold)) axe
```
> Description
```
Check if the item that the player and entity are holding on the main hand is an ax.
Detects DIAMOND_AXE, GOLD_AXE, IRON_AXE, STONE_AXE, and WOOD_AXE.

플레이어및 엔티티가 메인핸드에 들고있는 아이템이 도끼인지 체크합니다.
DIAMOND_AXE, GOLD_AXE, IRON_AXE, STONE_AXE, WOOD_AXE 를 감지합니다.
```
> Example
```
command /test:
    trigger:
        if player held axe:
            send "Held Axe"
        else if player not held axe:
            send "Not Held Axe"
```

- ### Holding shovel

> Syntax
```
%livingentity% (1¦(held|hold)|2¦(n[ot][ ]held|n[ot][ ]hold)) (shovel|spade)
```
> Description
```
Check if the item that the player and entity are holding on the main hand is a shovel.
Detects DIAMOND_SPADE, GOLD_SPADE, IRON_SPADE, STONE_SPADE, WOOD_SPADE.

플레이어및 엔티티가 메인핸드에 들고있는 아이템이 삽인지 체크합니다.
DIAMOND_SPADE, GOLD_SPADE, IRON_SPADE, STONE_SPADE, WOOD_SPADE 를 감지합니다.
```
> Example
```
command /test:
    trigger:
        if player held shovel:
            send "Held Shovel"
        else if player not held shovel:
            send "Not Held Shovel"
```

- ### Holding hoe

> Syntax
```
%livingentity% (1¦(held|hold)|2¦(n[ot][ ]held|n[ot][ ]hold)) hoe
```
> Description
```
Check if the item that the player and entity are holding on the main hand is better.
Detects DIAMOND_HOE, GOLD_HOE, IRON_HOE, STONE_HOE, and WOOD_HOE.

플레이어및 엔티티가 메인핸드에 들고있는 아이템이 낫인지 체크합니다.
DIAMOND_HOE, GOLD_HOE, IRON_HOE, STONE_HOE, WOOD_HOE 를 감지합니다.
```
> Example
```
command /test:
    trigger:
        if player held hoe:
            send "Held Hoe"
        else if player not held hoe:
            send "Not Held Hoe"
```

- ### isCoolSet

> Syntax
```
r[emain][ ]cool %string%
```
> Description
```
Check if there is still a cool time left to have String by name.

String을 이름으로 갖는 쿨타임이 남아있는지 체크합니다.
```
> Example
```
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

- ### Give

> Syntax
```
[s][kal][ ]give %itemstack% to %player%
```
> Description
```
Non-overlapping items such as weapons, armor, tools, and potion will be give in overlapping states.

무기, 방어구, 도구, 포션 등 겹쳐지지 않는 아이템들을 겹친 상태로 플레이어에게 지급합니다.
```
> Example
```
command /test:
    trigger:
        set {_item} to stone sword named "&eTEST"
        skal give {_item} to player
        
command /test:
    trigger:
        set {_item} to stone sword named "&dTEST2"
        sgive {_item} to player
```

## > Ver 1.0.1

- ### Fill

> Syntax
```
[s][kal][ ]fill %inventory% with %itemstack%
```
> Description
```
Add items to all slots in the inventory. The existing item remains.
인벤토리의 모든 슬롯에 아이템을 추가합니다. 기존의 아이템은 남아있습니다.
```
> Example
```
command /test:
    trigger:
        set {_item} to white glass pane named " "
        set {_inv} to inventory of player
        skal fill {_inv} with {_item}
        
command /test:
    trigger:
        set {_item} to white glass pane named " "
        set {_inv} to inventory of player
        sfill {_inv} with {_item}
```


- ### Fill all

> Syntax
```
[s][kal][ ]f[ill][ ]all %inventory% with %itemstack%
```
> Description
```
Add items to all slots in the inventory. Ignore existing items and overwrite them all.
인벤토리의 모든 슬롯에 아이템을 추가합니다. 기존 아이템을 무시하고 모두 덮어씌웁니다.
```
> Example
```
command /test:
    trigger:
        set {_item} to white glass pane named " "
        set {_inv} to inventory of player
        skal fill all {_inv} with {_item}
        
command /test:
    trigger:
        set {_item} to white glass pane named " "
        set {_inv} to inventory of player
        sfall {_inv} with {_item}
```

- ### Fill slot

> Syntax
```
[s][kal][ ]f[ill][ ]slot %integer% (~|to) %integer% of %inventory% with %itemstack%
```
> Description
```
Populates an item in the specified slot in the inventory. The existing item remains.
인벤토리의 지정한 슬롯에 아이템을 추가합니다. 기존의 아이템은 남아있습니다.
```
> Example
```
command /test:
    trigger:
        set {_item} to white glass pane named " "
        set {_inv} to inventory of player
        skal fill slot 0 ~ 10 of {_inv} with {_item}

command /test:
    trigger:
        set {_item} to white glass pane named " "
        set {_inv} to inventory of player
        sfslot 0 ~ 10 of {_inv} with {_item}
```

- ### Fill all slot

> Syntax
```
[s][kal][ ]f[ill][ ]a[ll][ ]slot %integer% (~|to) %integer% of %inventory% with %itemstack%
```
> Description
```
Populates an item in the specified slot in the inventory. Ignore existing items and overwrite them all.
인벤토리의 지정한 슬롯에 아이템을 추가합니다. 기존 아이템을 무시하고 모두 덮어씌웁니다.
```
> Example
```
command /test:
    trigger:
        set {_item} to white glass pane named " "
        set {_inv} to inventory of player
        skal fill all slot 0 ~ 10 of {_inv} with {_item}
        
command /test:
    trigger:
        set {_item} to white glass pane named " "
        set {_inv} to inventory of player
        sfaslot 0 ~ 10 of {_inv} with {_item}
```

- ### Knockback

> Syntax
```
[skal] knockback %entity% from %location% with ([power]|[speed]|[force]) %number%
```
> Description
```
Knockback entities from location
좌표로부터 엔티티를 넉백시킵니다.
```
> Example
```
on right click:
    knockback targeted entity from location of player with force 1.0
```

- ### Grab

> Syntax
```
[skal] grab %entity% to %location% with ([power]|[speed]|[force]) %number%
```
> Description
```
Grab entitis to location
좌표로 엔티티를 끌어당깁니다.
```
> Example
```
on right click:
    grab targeted entity to location of player with force 1.0
```

## > Ver 1.2.0

- ### Glowing

> Syntax
```
[skal] glow[ing] %entities% color[ed] %string% (to|for) %players%
```
> Required
```
[GlowAPI](https://www.spigotmc.org/resources/api-glowapi.19422/), [PacketListenerAPI](https://www.spigotmc.org/resources/api-packetlistenerapi.2930/)
```
> Description
```
Add a Glow Effect to an Entity
엔티티에 발광 효과를 추가합니다.

%string%
Black: BLACK, &0
Dark Blue: DARK_BLUE, &1
Dark Green: DARK_GREEN, &2
Dark Aqua: DARK_AQUA, &3
Dark Red: DARK_RED, &4
Dark Purple: DARK_PURPLE, &5
Gold: GOLD, &6
Gray: GRAY, &7
Dark Gray: DARK_GRAY, &8
Blue: BLUE, &9
Green: GREEN, &a
Aqua: AQUA, &b
Red: RED, &c
Purple: PURPLE, &d
Yellow: YELLOW, &e
White: WHITE, &f
None: NONE, OFF, DISABLE

```
> Example
```
on command /test:
    glow player color "DARK_AQUA" to player
    
on command /test:
    glow player color "&e" to player
    
on command /test:
    glow player color "disable" for player
```

# Expressions

## > Ver 1.0.0

- ### Display name

> Syntax
```
[the] d[isplay][ ]name of %player%
```
> Description
```
Gets the player's display name

플레이어의 디스플레이 이름을 가져옵니다
```
> Example
```
command /dname:
    broadcast dname of player
    
command /setDname [<string>]:
    set dname of player to arg 1
    
command /resetDname:
    delete dname of player
    reset dname of player
```

- ### Tab name

> Syntax
```
[the] t[ab][ ]name of %player%
```
> Description
```
Gets the name of the player's tab list

플레이어의 탭리스트 이름을 가져옵니다
```
> Example
```
command /tname:
    broadcast tname of player
    
command /setTname [<string>]:
    set tname of player to arg 1
    
command /resetTname:
    delete tname of player
    reset tname of player
```

- ### Cooltime

> Syntax
```
[the] cool[time] %string%
```
> Description
```
Create a cool time with a name for String.
Cool Time is not saved. Initialized on plugin reload

String 이름을 갖는 쿨타임을 생성합니다.
쿨타임은 저장되지 않습니다. 플러그인 리로드시 초기화됩니다
```
> Example
```
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

- ### Holding click

> Syntax
```
[the] h[old][ing][ ]time of %player%
```
> Description
```
Check the right click hold time.
Used in on click event
Check every 4tick.

우클릭 유지시 유지 시간을 확인합니다.
on Click 이벤트에서 작동합니다.
4tick 단위로 체크합니다.
```
> Example
```
on right click:
    if hold time of player > 100:
        send "Charging complete"
    
on right click:
    send "%htime of player%"
```

- ### Attack speed

> Syntax
```
[the] [s][kal][ ]attack speed of %player%
```
> Description
```
Set the player's default attack speed.
플레이어의 기본 공격 속도를 설정합니다.

Notes.
Default attack speed = Fist attack speed = 4
If attack speed of diamond sword = 1.6
Fist - Diamond sword = 2.4

set attack speed to 7
Fist attack speed = 7
diamond sword attack speed = 4.6
Fist - Diamond sword = 2.4

```
> Example
```
command /test:
    trigger:
        set {_AtkSpeed} to attack speed of player
        
command /test:
    trigger:
        add 1 to attack speed of player
        
command /test:
    trigger:
        remove 1 from attack speed of player
        
command /test:
    trigger:
        reset attack speed of player
        delete attack speed of player
```

- ### Attack damage

> Syntax
```
[the] [s][kal][ ]attack damage of %player%
```
> Description
```
Set the Player's default attack damage
플레이어의 기본 공격력을 설정합니다.
```
> Example
```
command /test:
    trigger:
        set {_AtkSpeed} to attack damage of player
        
command /test:
    trigger:
        add 1 to attack damage of player
        
command /test:
    trigger:
        remove 1 from attack damage of player
        
command /test:
    trigger:
        reset attack damage of player
        delete attack damage of player
```

# Types

























