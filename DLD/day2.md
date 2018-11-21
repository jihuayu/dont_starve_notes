# 饥荒mod制作（day2）
-----
## 创建主文件
1. 打开`test`文件夹，创建一个叫做`modmain.lua`的文件。
2. 在第一行写上`print("this is a test mod!")`。
3. 打开游戏，激活mod（关闭其他mod）。
4. 按`~`打开控制台，观察控制台输出。

### 效果如下：
![](image/2.1.png)
1. 观察输出格式，首先是输出的文件的位置（`mods/test/modmain.lua`）；然后是输出语句的位置，第一行第一个字符，；然后是输出内容`this is a test mod!`。
2. mod在加载的时就会运行`modmain.lua`的内容。