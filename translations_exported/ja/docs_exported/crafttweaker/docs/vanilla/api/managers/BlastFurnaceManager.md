# BlastFurnaceManager



crafttweakerのmod-idを持つmodによって追加されているクラスです。 従って、この機能を利用する場合はこのmodをインストールする必要があります。

## クラスのインポート
問題が発生した場合には、インポートが必要になります。とはいえ、お手数ですが予めインポートしておくほうが安全です。
```zenscript
craftweaker.api.BlastFurnaceManager
```

## 実装されたインターフェース
BlastFurnaceManager は以下のインターフェースを実装しています。 つまり、利用可能な任意のメソッドはこのクラスでも使用できます。
- [craftweaker.api.brackets.CommandStringDisplayable](/vanilla/api/brackets/CommandStringDisplayable)
- [crafttweaker.api.registrries.ICookingRecipeManager](/vanilla/api/managers/ICookingRecipeManager)
- [crafttweaker.api.registrries.IRecipeManager](/vanilla/api/managers/IRecipeManager)

## メソッド
### addJSONRecipe

提供されたIDataに基づいてレシピを追加します。 提供されたIDataはDataPack JSONを表し、IRecipeTypeシステムをサポートするDataPackのレシピを効果的に登録することができます。

```zenscript
blastFurnace.addJSONRecipe(name as String, data as crafttweaker.api.data.IData);
blastFurnace.addJSONRecipe("recipe_name", {item:<item:minecraft:gold_ore>.registryName},result:<item:minecraft:cooked_porkchop>.registryName,experience:0.35 as float, cookingtime:100});
```

| パラメータ | タイプ                                                    | 説明             |
| ----- | ------------------------------------------------------ | -------------- |
| 名前    | 文字列型                                                   | レシピの名前         |
| データ   | [crafttweaker.api.data.IData](/vanilla/api/data/IData) | jsonファイルを表すデータ |


### addRecipe

与えられたパラメータに基づいてレシピを追加します。

```zenscript
blastFurnace.addRecipe(name as String, output as crafttweaker.api.item.IItemStack, input as crafttweaker.api.item.IIngredient, xp as float, cookTime as int);
blastFurnace.addRecipe("wool2diamond", <item:diamond>, <tag:minecraft:wool>, 1.0);
```

| パラメータ | タイプ                                                                | 説明                 |
| ----- | ------------------------------------------------------------------ | ------------------ |
| 名前    | 文字列型                                                               | 新しいレシピの名前          |
| 出力    | [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack)  | レシピの IItemStack 出力 |
| input | [craftweaker.api.item.IIngredient](/vanilla/api/items/IIngredient) | レシピの原料入力           |
| xp    | float型                                                             | プレーヤーがどれだけXPを取得するか |
| 調理時間  | int                                                                | 調理にどれだけ時間がかかるか     |


### getRecipeByName

戻り値の型: [crafttweaker.api.recipes.WrapperRecipe](/crafttweaker/api/recipes/WrapperRecipe)

```zenscript
blastFurnace.getRecipeByName(name as String);
```

| パラメータ | タイプ  | 説明           |
| ----- | ---- | ------------ |
| 名前    | 文字列型 | 説明が提供されていません |


### getRecipesByOutput

戻り値の型: リスト&lt;[crafttweaker.api.recipes.WrapperRecipe](/crafttweaker/api/recipes/WrapperRecipe)&gt;

```zenscript
blastFurnace.getRecipesByOutput(output as crafttweaker.api.item.IIngredient);
```

| パラメータ | タイプ                                                                | 説明           |
| ----- | ------------------------------------------------------------------ | ------------ |
| 出力    | [craftweaker.api.item.IIngredient](/vanilla/api/items/IIngredient) | 説明が提供されていません |


### すべて削除

このレジストリ内のすべてのレシピを削除

```zenscript
blastFurnace.removeAll();
```

### removeByModo

レジストリ名modidに基づいてレシピを削除

```zenscript
blastFurnace.removeByModid(modid as String);
blastFurnace.removeByModid("minecraft");
```

| パラメータ | タイプ  | 説明              |
| ----- | ---- | --------------- |
| modid | 文字列型 | 取り除くべきレシピの<unk> |



追加された除外チェック付きのレジストリ名modidに基づいてレシピを削除すると、いくつか指定された以外のMod全体を削除できます。

```zenscript
blastFurnace.removeByModid(modied as String, exclude as crafttweaker.api.recipeFilter);
blastFurnace.removeByModid("minecraft", (name as string) => {return name == "orange_wool";});
```

| パラメータ | タイプ                                                                      | 説明               |
| ----- | ------------------------------------------------------------------------ | ---------------- |
| modid | 文字列型                                                                     | 取り除くべきレシピの<unk>  |
| 除外する  | [crafttweaker.api.recipe.RecipeFilter](/vanilla/api/recipe/RecipeFilter) | 排除されるレシピを教えてくれます |


### removeByName

レジストリ名に基づいてレシピを削除

```zenscript
blastFurnace.removeByName(name as String);
blastFurnace.removeByName("minecraft:furnace');
```

| パラメータ | タイプ  | 説明             |
| ----- | ---- | -------------- |
| 名前    | 文字列型 | 削除するレシピのレジストリ名 |


### removeByRegex

正規表現に基づいてレシピを削除

```zenscript
blastFurnace.removeByRegex(regex as String);
blastFurnace.removeByRegex("\\d_\\d");
```

| パラメータ | タイプ  | 説明        |
| ----- | ---- | --------- |
| Regex | 文字列型 | 正規表現と一致する |


### RemoveRecipe

出力に基づいてレシピを削除します。

```zenscript
blastFurnace.removeRecipe(output as crafttweaker.api.item.IItemStack);
blastFurnace.removeRecipe(<item:minecraft:glass>);
```

| パラメータ | タイプ                                                               | 説明     |
| ----- | ----------------------------------------------------------------- | ------ |
| 出力    | [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack) | レシピの出力 |



出力と入力に基づいてレシピを削除します。

```zenscript
blastFurnace.removeRecipe(output as crafttweaker.api.item.IItemStack, input as crafttweaker.api.item.IIngredient);
blastFurnace.removeRecipe(<item:minecraft:diamond>, <tag:minecraft:wool>);
```

| パラメータ | タイプ                                                                | 説明                 |
| ----- | ------------------------------------------------------------------ | ------------------ |
| 出力    | [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack)  | IItemStack レシピの出力。 |
| input | [craftweaker.api.item.IIngredient](/vanilla/api/items/IIngredient) | 削除するレシピの成分.        |



## プロパティー

| 名称            | タイプ  | ゲッターあり | セッターあり |
| ------------- | ---- | ------ | ------ |
| commandString | 文字列型 | true   | false  |

