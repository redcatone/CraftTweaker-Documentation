# MCIngredientConditionné

Cette classe a été ajoutée par un mod avec le mod-id `crafttweaker`. Vous devez donc avoir ce mod installé si vous voulez utiliser cette fonctionnalité.

## Importation de la classe
Il pourrait vous être nécessaire d'importer le paquet si vous rencontrez des problèmes (comme lancer un tableau), alors mieux être sûr que désolé et ajouter l'importation.
```zenscript
crafttweaker.api.item.MCIngredientConditioned
```

## Interfaces implémentées
MCIngredientConditioned implémente les interfaces suivantes. Cela signifie que toutes les méthodes disponibles peuvent également être utilisées dans cette classe.
- [crafttweaker.api.brackets.CommandStringDisplayable](/vanilla/api/brackets/CommandStringDisplayable)
- [format@@0 crafttweaker.api.item.Igredient](/vanilla/api/items/IIngredient)

## Méthodes
### aucun dégât

Type de retour : [crafttweaker.api.item.MCIngredientConditioned](/vanilla/api/items/MCIngredientConditioned)&lt;[crafttweaker.api.item.IIngredient](/vanilla/api/items/IIngredient)&gt;

```zenscript
null.anyDomage();
```

### Obtenir les objets restants

Quand cette pile d'ingrédients est fabriquée, que restera-t-il dans la grille ? Ne vérifie cependant pas si la pile correspond ! Utilisé par exemple dans net.minecraft.item.crafting.ICraftingRecipe

Type de retour : [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack)

```zenscript
null.getRemainingItem(stack as crafttweaker.api.item.IItemStack);
null.getRemainingItem(<item:minecraft:iron_ingot>);
```

| Paramètre | Type de texte                                                     | Libellé                                |
| --------- | ----------------------------------------------------------------- | -------------------------------------- |
| empilage  | [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack) | La pile à fournir pour cet ingrédient. |


### correspondances

Est-ce que la pile donnée correspond à l'ingrédient ?

Type de retour: booléen

```zenscript
null.matches(stack as crafttweaker.api.item.IItemStack);
null.matches(<item:minecraft:iron_ingot>);
```

| Paramètre | Type de texte                                                     | Libellé            |
| --------- | ----------------------------------------------------------------- | ------------------ |
| empilage  | [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack) | La pile à vérifier |



Type de retour: booléen

```zenscript
myMCIngredientConditioned.matches(stack as crafttweaker.api.item.IItemStack, ignoreDamage as boolean);
```

| Paramètre          | Type de texte                                                     | Libellé                    |
| ------------------ | ----------------------------------------------------------------- | -------------------------- |
| empilage           | [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack) | Aucune description fournie |
| Ignorer les dégâts | boolean                                                           | Aucune description fournie |


### seulement endommagé

Type de retour : [crafttweaker.api.item.MCIngredientConditioned](/vanilla/api/items/MCIngredientConditioned)&lt;[crafttweaker.api.item.IIngredient](/vanilla/api/items/IIngredient)&gt;

```zenscript
null.onlyDamaged();
```

### onlyIf

Type de retour : [crafttweaker.api.item.MCIngredientConditioned](/vanilla/api/items/MCIngredientConditioned)&lt;[crafttweaker.api.item.IIngredient](/vanilla/api/items/IIngredient)&gt;

```zenscript
null.onlyIf(uid en tant que chaîne, fonction en tant que function.Predicate<crafttweaker.api.item.IItemStack>);
```

| Paramètre | Type de texte                                                                                           | Libellé                    | Optionnel | Valeur par défaut |
| --------- | ------------------------------------------------------------------------------------------------------- | -------------------------- | --------- | ----------------- |
| uid       | Chaîne de caractères                                                                                    | Aucune description fournie | Faux      | `null`            |
| fonction  | function.Predicate&lt;[crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack)&gt; | Aucune description fournie | vrai      | `null`            |



## Propriétés

| Nom                | Type de texte                                                                                                  | A un Getter | A un Setter |
| ------------------ | -------------------------------------------------------------------------------------------------------------- | ----------- | ----------- |
| Ingrédient de base | TT                                                                                                             | vrai        | Faux        |
| Chaîne de commande | Chaîne de caractères                                                                                           | vrai        | Faux        |
| Condition          | [crafttweaker.api.item.IIngredientTransformer](/vanilla/api/items/IIngredientTransformer)&lt;T&gt; | vrai        | Faux        |
| Eléments           | [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack)[]                                            | vrai        | Faux        |

## Opérateurs
### OU

```zenscript
<tag:ingotIron> | autres que crafttweaker.api.item.IIngredient
```

| Paramètre | Type de texte                                                               | Libellé                    |
| --------- | --------------------------------------------------------------------------- | -------------------------- |
| autres    | [format@@0 crafttweaker.api.item.Igredient](/vanilla/api/items/IIngredient) | Aucune description fournie |

## Pistolet

| Type de résultat                                           | Est implicite |
| ---------------------------------------------------------- | ------------- |
| [crafttweaker.api.data.IData](/vanilla/api/data/IData)     | vrai          |
| [crafttweaker.api.data.MapData](/vanilla/api/data/MapData) | vrai          |

