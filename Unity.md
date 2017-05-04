---
# Unity の きほん (C#)
---
---
## *公式のチュートリアル、参考書、インターネットを利用する*
---
---
## ＜コンポーネントの取得＞
##### ＊インスペクタ―ビューでコンポーネントを確認する
```
GetComponent<コンポーネント名> ().変数名
```
```
text1.GetComponent<Text> ().text = "Hello World!!";
```
---
## ＜ほとんどのものは`GameObject`型として扱える（それぞれの型もある）＞
```
GameObject camera;
GameObject prefab;
GameObject button;
GameObject text;
```
---
## ＜外部から参照するときは`public`を付ける（逆は`private`）＞
```
public GameObject prefab;
```
---
## ＜`GameObject`を見つける＞
```
GameObject.Find("player");
```
---
## ＜オブジェクトの生成＞
```
GameObject go = (GameObject) Instantiate (gameobject);    /* gameobjectは何でもいい */
```
---
## ＜自分自身を削除＞
```
GameObject.Destroy(gameObject);
```
---
## ＜デバッグ＞
```
Debug.log("debug");
```
---
## ＜座標系は３つ＞
##### **ワールド座標** : 3D空間の座標
##### **スクリーン座標** : 画面のサイズ（解像度）、左下が原点
##### **ビューポート座標** : スクリーン座標の値を０～１にしたもの
---
## ＜スクリーン座標をワールド座標へ変換＞
```
Camera.main.ScreenToWorldPoint(new Vector3(x,y,z));
```
---
## <移動と回転＞
##### *移動や回転の方法はたくさんある*
```
gameobject.transform.Translate(x, y, z);    /* 並進 */
gameobject.transform.Rotate(rx, ry, rz);    /* 回転 */
```
---
## ＜座標取得＞
```
Vector3 posi = gameobject.transform.position;
posi.x += 1.0f;
```
---
## ＜衝突判定や重力など＞
##### Rigidbody とCollider のコンポーネントを付ける
##### **`2D`と`3D`用がある**
---
## ＜セーブ＞
##### 型（int,float,stringなど）をしっかり確認する
```
PlayerPrefs.SetInt("key1", val1);     /* 書き込み */
float val2 = PlayerPrefs.GetFloat("key2");    /* 読み込み */
```
---
## ＜キー入力＞
```
if(Input.GetKey(KeyCode.W)) {
  /* 'W'キーが押された */
}
/* Space, Return, UpArrowなど */
```
---
## ＜スマホでタッチ＞
```
if(Input.touchCount > 0) {/* タッチがあるとき */
  if(touch.phase == TouchPhase.Began) {
    /* タッチ開始時 */
  }
  else if(touch.phase == TouchPhase.Moved) {
    /* タッチ中で動いている */
  }
  else if(touch.phase == TouchPhase.Stationary) {
    /* タッチ中で静止している */
  }
  else if(touch.phase == TouchPhase.Ended) {
    /* タッチ終了時 */
  }
}
```
---
## ＜マウス入力＞
```
/* 0 : 左, 1 : 右, 2 : 中 */
if (Input.GetMouseButtonDown(0)) {
  /* 左マウスボタンが押された */
}
if (Input.GetMouseButton(0)) {
  /* 左マウスボタンが押されている */
}
if (Input.GetMouseButtonUp(0)) {
  /* 左マウスボタンが離された */
}
/* 座標取得 */
Vector3 posi = Input.mousePosition;    /* スクリーン座標系 */
```
