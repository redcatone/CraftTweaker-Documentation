# MCXpChange

crafttweakerのmod-idを持つmodによって追加されているクラスです。 従って、この機能を利用する場合はこのmodをインストールする必要があります。

## クラスのインポート
問題が発生した場合には、インポートが必要になります。とはいえ、お手数ですが予めインポートしておくほうが安全です。
```zenscript
crafttweaker.api.event.entity.player.PlayerXpEvent.MCXpChange
```

## Constructors
```zenscript
new crafttweaker.api.event.entity.player.PlayerXpEvent.MCXpChange(handler as function.Consumer<crafttweaker.api.event.entity.player.PlayerXpEvent.MCXpChange>);
```
| パラメータ   | タイプ                                                                                                                                           | 説明           |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ------------ |
| handler | function.Consumer<[crafttweaker.api.event.entity.player.PlayerXpEvent.MCXpChange](/vanilla/api/event/entity/player/PlayerXpEvent/MCXpChange)> | 説明が提供されていません |



## メソッド
### 取得金額

Returns int

```zenscript
myMCXpChange.getAmount();
```

### getEntityPlayer

戻り値 [crafttweaker.api.entity.player.MCPlayerEntity](/vanilla/api/entity/player/MCPlayerEntity)

```zenscript
myMCXpChange.getEntityPlayer();
```

### getPlayer

戻り値: `プレイヤー`

戻り値 [crafttweaker.api.entity.player.MCPlayerEntity](/vanilla/api/entity/player/MCPlayerEntity)

```zenscript
myMCXpChange.getPlayer();
```

### hasResult

このイベントが重要な結果値を期待するかどうかを決定します。 注: HasResult アノテーションを持つイベントでは、true を返すためにこのメソッドが自動的に追加されます。

戻り値ブール値

```zenscript
myMCXpChange.hasResult();
```

### isCancelable

この関数がキャンセル可能かどうかを判断します。 Returns: `If access to setCanceled should be allowed
 Note:
 Events with the Cancelable annotation will have this method automatically added to return true.`

戻り値ブール値

```zenscript
myMCXpChange.isCancelable();
```

### isCanceled

このイベントがキャンセルされ、実行を停止するかどうかを決定します。 戻り値: `現在の状態がキャンセルされました`

戻り値ブール値

```zenscript
myMCXpChange.isCanceled();
```

### setAmount

```zenscript
myMCXpChange.setAmount(amount as int);
```

| パラメータ | タイプ | 説明           |
| ----- | --- | ------------ |
| 金額    | int | 説明が提供されていません |


### setCanceled

```zenscript
myMCXpChange.setCanceled(cancel as boolean);
```

| パラメータ | タイプ      | 説明           |
| ----- | -------- | ------------ |
| キャンセル | boolean型 | 説明が提供されていません |



