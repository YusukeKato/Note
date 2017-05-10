---
# `Unity` から `ROS` を使ってロボットを動かす
# *調べたことのまとめ、間違っているかもしれない*
---
## < rosbridge >
#### ロボット側でrosbridgeを起動
#### IPアドレス、ポート番号確認
```
$ rosrun rosbridge rosbridge.py
```
#### JSON形式で通信するとROSのAPIに変換
#### 以下、wikiより例を示す
```
{ "op": "subscribe",
  "topic": "/cmd_vel",
  "type": "geometry_msgs/Twist"
}
```
---
## < WebSocket >
#### 通信規格の一つ。クライアントとサーバ間の接続を行う
#### Githubからダウンロードする(WebSocketで検索)
```
using WebSocketSharp;
```
```
var ws = new WebSocket("URL");
```
```
ws.OnOpen += (sender, e) => {
    /* 接続が確立したときのイベント */
};
ws.OnMessage += (sender, e) => {
    /* e.Data : テキスト文字列 */
    /* e.RawData : byte[] バイナリデータ */
};
ws.OnError += (sender, e) => {
    /* エラー時 */
    /* e.Message : エラーメッセージ */
    /* e.Exception : 原因のインスタンスを返す */
};
ws.OnClose += (sender, e) => {
    /* e.Code : 終了のステータスコード(ushort) */
    /* e.Reason : 理由を表す文字列 */
};

ws.Connect();    /* サーバ接続 */

ws.Send(data);    /* データ送信 */

ws.Close (code, reason);    /* 閉じる */

```

---
