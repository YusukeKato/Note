---
# Unity の きほん (C#)
---
---
## *公式のチュートリアル、参考書、インターネットを利用する*
---
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
---
### ＜座標は３つ＞
##### **ワールド座標** : 3D空間の座標
##### **スクリーン座標** : 画面のサイズ（解像度）、左下が原点
##### **ビューポート座標** : スクリーン座標の値を０～１にしたもの
---
### ＜スクリーン座標をワールド座標へ変換＞
```
Camera.main.ScreenToWorldPoint(new Vector3(x,y,z));
```
---
### <移動と回転＞
##### *移動や回転の方法はたくさんある*
```
gameobject.transform.Translate(x, y, z);    /* 並進 */
gameobject.transform.Rotate(rx, ry, rz);    /* 回転 */
```
---
### ＜座標取得＞
```
Vector3 posi = gameobject.transform.position;
posi.x += 1.0f;
```
---
### ＜衝突判定＞
##### Rigidbody とCollider をコンポーネント
##### **`2D`と`3D`用がある**
