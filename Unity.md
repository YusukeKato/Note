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
### 外部から参照するときは`public`を付ける（逆は`private`）
```
public GameObject prefab;
```
---
### ほとんどのものは`GameObject`型として扱える（それぞれの型もある）
```
GameObject player;
GameObject prefab;
GameObject button;
GameObject text;
```
