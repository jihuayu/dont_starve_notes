## 人物全解锁
----
- 关于人物是否解说的判断函数在`\data\scripts\playerprofile.lua`这个文件中，我们打开这个文件，发现里面有一个函数`IsCharacterUnlocked`是用来判断该人物是否解锁的，现在我们在mod中重新覆写这个函数。
```lua
    local PlayerProfile=require("playerprofile") -- 获取到playerprofile这个类
    function PlayerProfile:IsCharacterUnlocked(character) -- 修改这个类的方法IsCharacterUnlocked
        return true 
    end 
```