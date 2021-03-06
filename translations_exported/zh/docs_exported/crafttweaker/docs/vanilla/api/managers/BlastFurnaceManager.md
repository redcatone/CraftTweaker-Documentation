# BlastFurnaceManager #高炉合成表管理



这个类由mod-id为`crafttweaker`的模组添加. 因此，如果要使用此功能，则需要安装此mod。

## 导入相关包
如果遇到任何问题（例如强制转换数组），则可能需要导入软件包，因此，最好的方式就是导入包支持。
```zenscript
crafttweaker.api.BlastFurnaceManager
```

## 已实现的接口
BlastFurnaceManager实现了以下接口。 这意味着对这个接口可用的任何方法也可以在此类上使用。
- [crafttweaker.api.brackets.CommandStringDisplayable](/vanilla/api/brackets/CommandStringDisplayable)
- [crafttweaker.api.registries.ICookingRecipeManager](/vanilla/api/managers/ICookingRecipeManager)
- [crafttweaker.api.registries.IRecipeManager](/vanilla/api/managers/IRecipeManager)

## 方法
### addJSONRecipe #添加JSON配方

基于提供的IData添加配方 提供的 IData 应该代表一个JSON数据包 ,这有效地允许您注册任何支持 IRecipeType 系统的 DataPack配方。

```zenscript
blastFurnace.addJSONRecipe(name as String, data as craftweaker.api.data.IData);
blastFurnace.addJSONRecipe("recipe_name", {component:{item:<item:minecraft:gold_ore>.registryName},result:<item:minecraft:cooked_porkchop>.registryName,experience:0.35 as float, cookingtime:100});
```

| 参数   | 类型                                                     | 描述           |
| ---- | ------------------------------------------------------ | ------------ |
| 名称   | 字符串[string]                                            | 配方名称         |
| data | [crafttweaker.api.data.IData](/vanilla/api/data/IData) | 代表json 文件的数据 |


### 添加配方

添加基于给定参数的合成表

```zenscript
blastFurnace.addRecipe(name as String, output as crafttweaker.api.item.IItemStack, input as crafttweaker.api.item.IIngredient, xp as float, cookTime as int);
#添加合成表的格式
blastFurnace.addRecipe("wool2diamond", <item:diamond>, <tag:minecraft:wool>, 1.0, 0);
#示例显示了如何实现将羊毛在高炉中烧制成钻石并且获得1.0的经验
```

| 参数             | 类型                                                                | 描述         |
| -------------- | ----------------------------------------------------------------- | ---------- |
| 名称             | 字符串[string]                                                       | 新的合成表名称    |
| output（输出）     | [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack) | 合成表的输出物品id |
| input（输入）      | [制造商.api.item.IIngredient](/vanilla/api/items/IIngredient)        | 合成表的输入成分   |
| xp             | 浮点数                                                               | 玩家获得多少经验   |
| cookTime #烧制时间 | 整数                                                                | 烧制需要多长时间   |


### getRecipeByName

返回类型： [craftbiner.api.配方。WrapperRecipe](/crafttweaker/api/recipes/WrapperRecipe)

```zenscript
blastFurnace.getRecipeByname(名称为字符串)；
```

| 参数 | 类型          | 描述                      |
| -- | ----------- | ----------------------- |
| 名称 | 字符串[string] | No description provided |


### getRecipesBy输出

返回类型：列表&lt;[craftbinstrues.WrapperRecipe](/crafttweaker/api/recipes/WrapperRecipe)&gt;

```zenscript
blastFurnace.getRecipesByOutput(输出为 craftweeper.api.item.IIngredient);
```

| 参数         | 类型                                                         | 描述                      |
| ---------- | ---------------------------------------------------------- | ----------------------- |
| output（输出） | [制造商.api.item.IIngredient](/vanilla/api/items/IIngredient) | No description provided |


### 全部移除

删除此注册表中的所有配方

```zenscript
blastFurnace.removeAll();
```

### 移除 ByModid

删除基于注册表名称莫迪的配方

```zenscript
blastFurnace.removeByModed(modand as String);
blastFurnace.removeByModed("minecraft");
```

| 参数  | 类型          | 描述          |
| --- | ----------- | ----------- |
| 莫多德 | 字符串[string] | 已删除配方的 modo |



通过添加排除检查，删除基于注册表名称的配方，这样除了指定的几个选项之外，您可以删除整个模组。

```zenscript
blastFurnace.removeByModed(modian as String, exclusion as craftweepe.RecipeFilter);
blastFurnace.removeByModed("minecraft", (name as string) => {return name == "orange_wool";});
```

| 参数  | 类型                                                              | 描述          |
| --- | --------------------------------------------------------------- | ----------- |
| 莫多德 | 字符串[string]                                                     | 已删除配方的 modo |
| 不包含 | [制作器.api.recipe.RecipeFilter](/vanilla/api/recipe/RecipeFilter) | 要避免被移除的配方。  |


### removeByName

删除基于注册表名称的配方

```zenscript
blastFurnace.removeByname(名称为字符串);
blastFurnace.removeByname("minecraft:furnace");
```

| 参数 | 类型          | 描述           |
| -- | ----------- | ------------ |
| 名称 | 字符串[string] | 要删除的配方的注册表名称 |


### removeByRegex

基于正则表达式删除配方

```zenscript
blastFurnace.removeByRegex(regex as String);
blastFurnace.removeByRegex("\d_\\d");
```

| 参数    | 类型          | 描述      |
| ----- | ----------- | ------- |
| 正则表达式 | 字符串[string] | 正则表达式匹配 |


### 删除合成表

移除基于其输出的配方。

```zenscript
blastFurnace.removeRecipe(输出为 craftweeper.api.item.IItemStack);
blastFurnace.removeRecipe(<item:minecraft:glass>);
```

| 参数         | 类型                                                                | 描述    |
| ---------- | ----------------------------------------------------------------- | ----- |
| output（输出） | [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack) | 配方的输出 |



移除基于输出和输入的合成表

```zenscript
blastFurnace.removeRecipe(output as crafttweaker.api.item.IItemStack, input as crafttweaker.api.item.IIngredient);
#删除合成表的格式
blastFurnace.removeRecipe(<item:minecraft:diamond>, <tag:minecraft:wool>);
#由输入为羊毛输出为钻石的方式定位并且删除这个合成表
```

| 参数         | 类型                                                                | 描述          |
| ---------- | ----------------------------------------------------------------- | ----------- |
| output（输出） | [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack) | 合成表的输出物品id. |
| input（输入）  | [制造商.api.item.IIngredient](/vanilla/api/items/IIngredient)        | 要移除的配方的成分。  |



## 参数

| 名称                   | 类型          | 可获得  | 可设置   |
| -------------------- | ----------- | ---- | ----- |
| commandString #命令字符串 | 字符串[string] | true | false |

