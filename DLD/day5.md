# 饥荒mod制作（day5）
---- 

## 第一个工具
1. 打开我们写一半的`growingswordlite.lua`,继续书写。
2. 在函数`fn`中添加内容：
```lua
    inst:AddComponent("tool") -- 添加工具控件
    inst.components.tool:SetAction(ACTIONS.CHOP) -- 添加砍树的动作
```

### 效果如下：
![](image/5.1.png) 成功的砍树

3. 但是这个武器还是没有耐久，也就是说无限耐久，我们需要再给他增加一个控件让他拥有耐久。
4. 在fn继续添加内容：

```lua
    inst:AddComponent("finiteuses") -- 添加控件耐久
    inst.components.finiteuses:SetMaxUses(100)  -- 添加最大耐久
    inst.components.finiteuses:SetUses(100)  -- 添加当前耐久
    inst.components.finiteuses:SetOnFinished(onfinished) -- 设置耐久归零调用的函数
    inst.components.finiteuses:SetConsumption(ACTIONS.CHOP, 1) -- 设置耐久消耗途径和速度（每砍一次减少一点耐久）
```

### 效果如下：
![](image/5.2.png) 满耐久
![](image/5.3.png) 砍树3次后的耐久

5. 但是我们这样把最大耐久直接写在代码里不好修改，我们可以这么修改：

```lua
    local function fn(Sim)
        [···]
        inst.components.finiteuses:SetMaxUses(TUNING.GROWINGSWORDLITE_USES) --从TUNING中获取GROWINGSWORDLITE_USES的值
        inst.components.finiteuses:SetUses(TUNING.GROWINGSWORDLITE_USES) 
        [···]
    end
    TUNING.GROWINGSWORDLITE_USES = 100 -- 这行代码可以放在任意会在上面代码之前运行的位置上
```

