---
# Unity の きほん (C#)
---
### ＜コンポーネントの取得＞
##### ＊インスペクタ―ビューでコンポーネントを確認する
```
GetComponent<コンポーネント名> ().変数名
```
```
text1.GetComponent<Text> ().text = "Hello World!!";
```
---
### ＜ほとんどのものは`GameObject`型として扱える（それぞれの型もある）＞
```
GameObject camera;
GameObject prefab;
GameObject button;
GameObject text;
```
---
### ＜外部から参照するときは`public`を付ける（逆は`private`）＞
```
public GameObject prefab;
```
---
### ＜`GameObject`を見つける＞
```
GameObject.Find("player");
```
---
### ＜オブジェクトの生成＞
```
GameObject go = (GameObject) Instantiate (prefab);
```
---
### ＜自分自身を削除＞
```
GameObject.Destroy(gameObject);
```
---
### ＜デバッグ＞
```
Debug.log("debug");
```
