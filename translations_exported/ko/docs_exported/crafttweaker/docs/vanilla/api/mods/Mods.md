# Mods

This class was added by a mod with mod-id `crafttweaker`. So you need to have this mod installed if you want to use this feature.

## Importing the class
It might be required for you to import the package if you encounter any issues (like casting an Array), so better be safe than sorry and add the import.
```zenscript
crafttweaker.api.mods.Mods
```

## Methods
### getMod

Gets a specific mod

 Returns: `a specific MCModInfo`

Return type: [crafttweaker.api.mods.ModInfo](/vanilla/api/mods/ModInfo)

```zenscript
myMods.getMod(modid as String);
myMods.getMod("minecraft");
```

| Parameter | Type   | Description             |
| --------- | ------ | ----------------------- |
| modid     | String | No description provided |


### isModLoaded

Checks if a mod is laoded

 Returns: `true if the mod is loaded`

Return type: boolean

```zenscript
myMods.isModLoaded(modid as String);
myMods.isModLoaded("minecraft");
```

| Parameter | Type   | Description    |
| --------- | ------ | -------------- |
| modid     | String | modid to check |



## Properties

| 이름   | Type                                                                               | Has Getter | Has Setter |
| ---- | ---------------------------------------------------------------------------------- | ---------- | ---------- |
| mods | List&lt;[crafttweaker.api.mods.ModInfo](/vanilla/api/mods/ModInfo)&gt; | true       | false      |
| size | int                                                                                | true       | false      |

