---
# Unity の きほん (C#)
---
---
### *公式のチュートリアル、参考書、インターネットなど情報はたくさんある*
### *ここにはよく使うものをまとめる*
---
## ＜ Asset Store ＞
#### `Asset Store` には、無料のものもあるので探してみるとよい
#### 公式チュートリアルのプロジェクトもある
#### Unityエディタ上から開ける
---
## ＜スクリーンのサイズ＞ はじめにやっておく
##### `BuildSetting` で　プラットフォームを選択
##### その後、`game view` で画面サイズを選択
---
## ＜忘れがちなこと＞
##### BuildSettingで、必要な `Scene` すべてを登録する
##### `Company Name` , `Product Name` を変更する
---
## ＜コンポーネントの取得＞
##### ＊ `Inspector` で `component` を確認する
```
GetComponent<コンポーネント名> ().変数名
```
```
text1.GetComponent<Text> ().text = "Hello World!!";
```
---
## ＜ほとんどのものは `GameObject` として扱える（それぞれのクラスもある）＞
```
GameObject camera;
GameObject prefab;
GameObject button;
GameObject text;
```
```
public Text text2;
//-----------------------//
text2.text = "hello world!!";
```
---
## ＜外部から参照するときは `public` を付ける（逆は `private` ）＞
```
public GameObject prefab;
```
---
## ＜ `GameObject` を見つける＞
```
GameObject.Find("player")
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
### **理解が曖昧なところ**
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
##### `Rigidbody` と `Collider` の `component` を付ける
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
---
## ＜オブジェクトを有効・無効にする＞
##### `Inspector` でオブジェクト名の左にあるチェックでも可能
##### オブジェクトを無効にすると、それに付いているスクリプトも無効になるので気をつける
```
gameobject.SetActive(true);     /* 有効 */
gameobject.SetAcitve(false);    /* 無効 */
```
---
## ＜１フレームの時間を取得＞
##### float型
```
delta += Time.deltaTime;
```
---
## ＜画像の使用＞
##### 画像をドラック＆ドロップで `project` に入れる
##### `Inspector` で `Texture type` を変更。 `Sprite(2D & UI)` など
---
## ＜スクリプトにアクセス＞
```
GetComponent<コンポーネント名> ()     /* ゲームオブジェクトを参照して、スクリプトにアクセス */
FindObjectOfType<スクリプト名> ()    /* スクリプトを参照して、スクリプトにアクセス */
```
---
## ＜音＞
##### `AudioSource` から出て、 `AudioListener` で聴く
```
public AudioClip audioClip1;
private AudioSource audioSource;
//---------------------------------------------------------//
audioSource = gameObject.GetComponent<AudioSource>();
audioSource.clip = audioClip1;
audioSource.Play ();    /* 方法１ */
audioSource.PlayOneShot(audioClip1);    /* 方法２ */
```
---
## ＜シーン遷移＞
```
using UnityEngine.SceneManagement;
//-------------------------------------------
SceneManager.LoadScene("Scene_Name");
```
---
## ＜ 乱数 ＞
#### MIN <= val <= MAX　( float, int )
```
val = Random.Range(MIN, MAX);
```
---
## ＜ 色 ＞
#### コンポーネントをしっかり確認する
```
Color Blue = new Color(0.6f, 0.8f, 0.6f, 1.0f);
prefab.GetComponent<Renderer> ().material.color = Blue;
```
---
## ＜　N 秒待ってから関数処理　＞
```
StartCoroutine("function");
IEnumerator function(){
    yield return new WaitForSeconds(5.0f);    /* 5秒待つ */
}
```
---
## ＜　rigidbody　＞
```
rigidbody.AddForce(Vector3);
AddRelativeForce(Vector3);
AddTorque(Vector3);
AddRelativeTorque(Vector3);

```
```
OnCollisionEnter
OnTriggerEnter
```
---
## ＜ transform ＞
#### `transform` は親に対して相対的に設定される
---
## ＜ Euler と Quaternion ＞
#### `Unity` 内部では `Quaternion` で表現されている
#### `inspector ウィンドウ` では人が見てわかるように `Euler` で表現されている
---
## ＜ 正しい `Euler` 角の使いかた ＞
```
float x;
void Update () {
    x += Time.deltaTime * 10;
    transform.rotation = Quaternion.Euler(x,0,0);
}
```
---
## ＜  InputManager ＞
#### `Edit > Project Settings > Input`
#### `GetAxis` は `float` 型で返す
```
float dx = Input.GetAxis ("Horizontal");
float dy = Input.GetAxis ("Vertical");
```
---
## ＜ タグで `GameObject` を見つける ＞
```
GameObject[] boids = GameObject.FindGameObjectsWithTag ("boid");
```
---
