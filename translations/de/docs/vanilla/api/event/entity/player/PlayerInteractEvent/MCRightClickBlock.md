# MCRightClickBlock

Diese Klasse wurde von einer Mod mit mod-id `crafttweaker` hinzugefügt. Wenn Sie diese Funktion nutzen möchten, müssen Sie diese Mod installiert haben.

## Diese Klasse importieren
Es kann erforderlich sein, dass Sie das Paket importieren, wenn Sie irgendwelche Probleme haben (wie zum Beispiel ein Array zu bearbeiten), also besser sicher sein als bedauern und fügen Sie den Import.
```zenscript
crafttweaker.api.event.entity.player.PlayerInteractEvent.MCRightClickBlock
```

## Konstrukteure
```zenscript
neue crafttweaker.api.event.entity.player.PlayerInteractEvent.MCRightClickBlock(Handler als Funktion.Verbraucher<crafttweaker.api.event.entity.player.PlayerInteractEvent.MCRightClickBlock>);
```
| Parameter | Type                                                                                                                                                                    | Beschreibung                 |
| --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- |
| handler   | function.Consumer<[crafttweaker.api.event.entity.player.PlayerInteractEvent.MCRightClickBlock](/vanilla/api/event/entity/player/PlayerInteractEvent/MCRightClickBlock)> | Keine Beschreibung angegeben |



## Methoden
### getEntityPlayer

Gibt [craftweaker.api.entity.player.MCPlayerEntity](/vanilla/api/entity/player/MCPlayerEntity) zurück

```zenscript
myMCRightClickBlock.getEntityPlayer();
```

### getFace

Gibt `das an dieser Interaktion beteiligte Gesicht zurück. Für alle nicht-blockierten Interaktionen wird diese Null zurückgegeben.`

Gibt [craftweaker.api.util.Direction](/vanilla/api/util/Direction)

```zenscript
myMCRightClickBlock.getFace();
```

### getItemStack

Gibt zurück: `Der Gegenstand ist an dieser Interaktion beteiligt, {` @code ItemStack.EMPTY} wenn die Hand leer war.

Gibt [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack) zurück

```zenscript
myMCRightClickBlock.getItemStack();
```

### getPlayer

Rückgaben: `Spieler`

Gibt [craftweaker.api.entity.player.MCPlayerEntity](/vanilla/api/entity/player/MCPlayerEntity) zurück

```zenscript
myMCRightClickBlock.getPlayer();
```

### getPos

Wenn die Interaktion auf einer Entität war, wird ein BlockPos zentriert auf der Entität. Wenn die Interaktion auf einem Block war, wird die Position des Blocks sein. Ansonsten wird ein BlockPos zentriert auf dem Spieler. Wird nie null sein. Gibt `die Position zurück, die an dieser Interaktion beteiligt ist.`

Gibt [craftweaker.api.util.BlockPos](/vanilla/api/util/BlockPos) zurück

```zenscript
myMCRightClickBlock.getPos();
```

### hasergebnis

Legt fest, ob dieses Ereignis einen signifikanten Ergebniswert erwartet. Hinweis: Ereignisse mit der HasResult-Anmerkung werden diese Methode automatisch hinzugefügt, um wahr zurückzugeben.

Rückgabewert boolesch

```zenscript
myMCRightClickBlock.hasResult();
```

### isabbrechbar

Legen Sie fest, ob diese Funktion überhaupt abgebrochen werden kann. Gibt zurück: `Wenn der Zugriff auf setCanceled erlaubt sein sollte
 Hinweis:
 Ereignisse mit der abbrechbaren Anmerkung werden diese Methode automatisch hinzugefügt, um true zurückzugeben.`

Rückgabewert boolesch

```zenscript
myMCRightClickBlock.isAbbrechbar();
```

### ist abgebrochen

Legen Sie fest, ob dieses Ereignis abgebrochen wird und nicht mehr ausgeführt werden soll. Rückgabe: `Der aktuell abgebrochene Status`

Rückgabewert boolesch

```zenscript
myMCRightClickBlock.isAbbrecht();
```

### abgebrochen

```zenscript
myMCRightClickBlock.setCanceled(als Boolean abgebrochen);
```

| Parameter   | Type    | Beschreibung                 |
| ----------- | ------- | ---------------------------- |
| abgebrochen | boolean | Keine Beschreibung angegeben |



