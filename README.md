# -这里是阿西用来练习制作mcrpg/pve地图的项目，最终目标是做出一个与《永夜》同等技术力的mcpve地图.
_<p align="center">学习的过程以及感悟会在这里列出来</p>_  

## __2024/5/27__  
1.Readme的编写基本规范。  
2.项目的创建和更新。  
3.了解到如何使用model/item中的json来调整武器的位置。其中的translation：[右,前,上],scale:[长(水平）,高（垂直）,厚],rotation说不准，慢慢转吧。

## __2024/5/28__ 
1.了解如何使用CustomModelData自定义物品材质。  
2.了解mc材质包和数据包的结构。  
3.使用blockbench修改物品模型。

## __2024/5/29__ 
1.了解到blockbench的绘画功能。  
2.了解了一些基础指令（tp say execute ）还有一些目标选择器。

## __2024/5/31__（test-0)
1.制作了第一张练习用地图test-0。

## __2024/5/31__（test-1)
1.继续解决test-0的问题。
2.复习了一些指令。
3.了解了level.data的作用。

## __2024/6/1__（test-2)
1.学习了解如何使用blockbench制作自定义物品模型，参考他人视频制作了蜂蜜剑，具备动态材质。  

## __2024/6/1__
1.多人游戏出现了问题（循环/保持开启的命令方块：/execute as @a at @s if block ~ -60 ~ black_woof unless score @s diqu = @s 1 run title....)，当游戏为多人时会发生一些问题，我自己在进入指定区域时该指令只会触发一次，但队友会无限触发。（猜测，队友的计分板“1”的分数不为1导致的）  
结论：所有scoreboard的初始化最好写入数据包的load.json中防止忘记。其次就是在execute中，各条件子命令都需要被触发才会执行最后的run。


