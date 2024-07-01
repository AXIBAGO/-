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
1.制作了第一张练习用地图test-0（1.20.1）。

## __2024/5/31__（test-1)
1.继续解决test-0的问题。
2.复习了一些指令。
3.了解了level.data的作用。

## __2024/6/1__（test-2)
1.学习了解如何使用blockbench制作自定义物品模型，参考他人视频制作了蜂蜜剑，具备动态材质。  

## __2024/6/1__（test-3）
1.多人游戏出现了问题（循环/保持开启的命令方块：/execute as @a at @s if block ~ -60 ~ black_woof unless score @s diqu = @s 1 run title....)，当游戏为多人时会发生一些问题，我自己在进入指定区域时该指令只会触发一次，但队友会无限触发。（猜测，队友的计分板“1”的分数不为1导致的）  
结论：所有scoreboard的初始化最好写入数据包的load.json中防止忘记。其次就是在execute中，各条件子命令都需要被触发才会执行最后的run。  
2.将地图中的命令方块优化到数据包中。

## __2024/6/1__
1.了解学习战利品表，物品修饰符，以及json格式和nbt格式。

## __2024/6/3__
1.学习了/data的基本用法，感觉data modify很强大，可以实现一些自定义功能。
2.看到一种通过战利品表实现百分率效果的方法。

## __2024/6/4__（test-4）
1.新增悬浮文字；成书、告示牌上的可交互文字；小板凳；HUh猫。

## __2024/6/5__（test-5）
1.改善了boss出场方式。  
2.继续学习指令。了解了谓词，基本可以实现全命令的概率触发。所以说版本是不断更新的，老方法不一定是最好的，一定要多看。  
3.看到一个很牛逼的指令，1.20.2更新的，叫宏命令，遂决定升级版本到1.20.2，但物品堆叠组件尚不完善，所以暂时不打算升级到1.20.5。

## __2024/6/6__
1.如果使用宏命令获取实体的生命值，数据类型会很直白，也就是说原本是什么类型，他就是什么类型。想用这个做生命值显示的话，虽然指令很简短，但显示出来的效果很差，因为生命值是一个f类型的数据，会显示成1.1232132143421这样的。一种解决思路就是使用官方的scoreboard直接获取实体生命，这样生命值就会是整形。  
2.实体的CustomName无法直接解析文本组件，但是方块实体就可以，比如说oak_sign的messages就可以解析文本套件后，将解析后的文本填入messages中，最后再使用data modify将这段文本转移至实体的CustomName之中。也就是说这种方法可以代替实体解析那些解析不了的文本组件。

## __2024/6/9__（test-6）
1.新增特定怪物血量显示。

## __2024/6/9__（test-7）
1.新增指定地点使用书对物品进行改名。

## __2024/6/12__
1.一直没放材质包，补一个。

## __2024/6/19__
1.一个小知识：如果想实现在非A条件下对实体e执行某个函数可以这样写  
  在A条件下给e加上独特标签  
  对没有独特标签的实体执行函数  
  移除e的独特标签  
  这样的好处是什么？有些条件无法直接写出来，比如“如果实体身上没有人，那么。。”，但是“如果实体身上有人”可以写出来，于是通过标签法可以实现！的功能。  
  
## __2024/6/23__（test-8)
1.做了一个丐版悬浮菜单，以后有望优化。  
2.以后写数据包倒是可以用思维导图，这样脑子不容易乱。  
3.没找到aj和粒子的教程，感觉很难。  
4.终于找到vscode图标mc风格的，叫Datapack Icons

## __2024/6/23__（test-8)  
1.做了一个饱和度显示数据包。  
2.大致了解如何使用aj制作mob，但ai这块目前使用wandering_trade有一点点卡。  
3.aj官方的discord有一个mobai可以试试。

  

  



